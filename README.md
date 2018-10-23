AngularJS2+
====

# install
- npm
    - sudo apt-get install npm
- angular-cli
    - sudo npm install -g typescript
    - sudo npm install -g @angular/cli
- node upgrade
    - sudo npm cache clean -f
    - sudo npm install -g n
    - sudo n stable
    - sudo n latest
    - sudo apt-get install --reinstall nodejs-legacy

# github
- create new repository 
- install github for ubuntu
    - sudo add-apt-repository ppa:git-core/ppa
    - sudo apt-get update
    - sudo apt-get dist-upgrade
    - sudo apt-get install git-core

# new project
- ng new imon

# template
- index.html
    - <app-root></app-root>

# component
- app.component.ts
    - @Component
    - selector: 'app-root'
    - templateUrl: './app.component.html'
    - styleUrls: ['./app.component.css']

# Module & Bootstrapping
- Root Module 
- Module
    - @NgModule
    - declarations
        - Component, Directive, Pipe declare, use this module
    - imports
        - Dependency Third Party Modules
    - providers
    - bootstrap: [AppComponent]

# Angular Material
- npm install --save @angular/material @angular/cdk
- --save or --save-dev
- npm install --save @angular/animations
- npm install --save hammerjs

# Data Binding
- Two Way Data Binding
    - [(ngModel)]="keyword"
    - (ngModelChange)="inputChange()"
        - korean issue : COMPOSITION_BUFFER_MODE
- One Way Data Binding
    - Interpolation: Component -> View
        - {{ value }}
    - Property binding : View DOM HTML Element property
        - [property]="value"
        - <button ... [disabled]="book.bprice > 20000">바로 구입</button>
    - Event binding : View DOM Event handler => Component Method
        - (event)="function"
- Template Reference Variable
    - <input matInput #inputKeyword placeholder="Search Keyword">
    - <button mat-raised-button color="warn" (click)="setKeyword(inputKeyword.value)">Search!</button>
- Safe Navigation Operator
    - {{ book?.btitle }}
        - if null : prevent error

# Material Table

# Data Share
- @Input
    - parent => child component data share
    - parent html
        - <app-search-box [bookCategory]="displayCategoryName"></app-search-box>
    - child component
        - @Input() bookCategory:string;
    - child html
        - <ng-container *ngIf="bookCategory != null"> {{bookCategory}} </ng-container>
    - if process : @Input() on setter method
        - @Input()
          set bookCategory(value: string) {
              if( value != null ) {
                  this._bookCategory = 'category: ' +value;
              } else {
                  this._bookCategory = value;
              }
          }
- @Output
    - child => parent component data share
    - EventEmitter
    - child component
        - @Output() searchEvent = new EventEmitter();
        - push keyword button
            - setKeyword(keyword: string): void {
                  this.keyword = keyword;
                  this.searchEvent.emit({
                      keyword : `${this.keyword}`,
                      category: `${this._bookCategory.replace('category: ','')}`
                  });
              }
    - parent component
        - 
- @ViewChild
