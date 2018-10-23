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
