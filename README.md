# Tradingroom

## Nodejs repo for live-trading app with the following stack

- Angular v.1.6.6
- Express
- Socket.io
- Semantic UI
- MongoDB

_*Do not run bower install for front-end dependencies as bower installs an upgraded version of angular which breaks the app.*_

Latest copy of **`/node_modules`** and **`/app-frontend/lib`** is available **[here]()** alternatively get a copy from one of the devs and use them instead.

---

# Table of Contents

1. [Getting Started](#getting-started)
1. [Rules](#rules)
1. [Roadmap](#roadmap)
1. [Tutorials](#tutorials)
1. [App Architecture](#app-architecture)
1. [Detailed API reference](#detailed-api-reference)

---

# Getting Started

1. `git checkout style-guide`
1. Place `config.json` in tradingroom (root) folder
1. Replace node_modules\* (root) folder
1. Replace lib folder\* inside app-frontend/lib
1. `npm install`

_\*For the config, node_modules and lib files check with dev team for latest packages_

Redis Connection Error on Windows [follow this tutorial.](https://medium.com/@kasunprageethdissanayake/installing-redis-x64-3-2-100-on-windows-and-running-redis-server-94db3a98ae3d)

---

# Rules

## Team

1. Don't suffer in silence. Ask if you need anything at all.

## Git

1. Before you push any commit must check status of your local commits v/s remote by running git status.
2. Always follow this order .i.e **never** push without pulling first (in case remote is ahead of your local)
   1. `git commit`
   1. `git pull`
   1. `git push`

---

## Code Style

1. Do not use `$scope` variables if you do not intend to use them in jade. For eg. `$scope.something = []` if this is not used in jade then it rather be let something = [] in controller.
1. Do your best to write reusable functions and use services via dependency injection for functions that will be repeated
1. Do not use `$rootScope` unless absolutely necessary
1. Do not create new `$scope.$broadcast` or `$scope.$emit` or `$scope.$watch` events unless absolutely necessary. Find ways to reuse existing event listeners. For eg. take a look at how $scope.$on('Child:Update', ...) is reused with switch/case in controller.js
1. Avoid inline CSS in jade as much as possible. For colors refer to `dark-schema.css` and `light-schema.css` files and for alignment, and global styling refer to `master-template.css` file

---

## API

1. We can fetch and post data to backend using Express http API or [socket.io](https://socket.io/) but there are some pointers to choose either one.
1. Use Express http API for large payloads for eg. backend to return an array of aggregation with lots of objects
1. Use socket.io for smaller payloads as socket is real-time and large payloads may crash the socket due to the time it takes to curate data.
1. We already have too many socket listeners so do not create new socket events unless absolultey necessary. Use existing socket listeners as much as possible. For eg. take a look at how switch/case is used in Manage:Server socket listener for maximum effect.

## Testing

1. TBC

---

# Tutorials

1. [AngularJS](https://www.w3schools.com/angular/default.asp)
1. [Express](https://expressjs.com/en/starter/hello-world.html)
1. [Socket.io](https://socket.io/docs/)
1. [MongoDB](https://www.mongodb.com/blog/post/getting-started-with-mongodb-atlas)
1. [Redis](https://redis.io/topics/quickstart)
1. [Semantic UI](http://semantic-ui.com/elements/button.html)

---

# Code Architecture

Explaining the architecture of the tradingroom app?

---

# Detailed API reference

Detailed API links ?

---
