Simple and elegant component-based UI library []codeclimate-url Framework Size Comparison | Framework | Version | Minified Size (gzip) | |------------------------------------------------|-----------------|----------------------| | @angular/core + Polyfills | 6.0.1 | 141.56kb | | Ember | 2.18.2 | 121.84kb | | Polymer + Web Components Polyfill Lite | 1.8.0 | 66.3kb | | React + Map and Set Polyfills | 16.3.2 | 43.47kb | | Web Components Polyfill | 0.7.24 | 33.68kb | | Vue | 2.5.16 | 31.64kb | | Riot | 3.10.3 | 10.78kb | | Inferno | 5.1.1 | 7.79kb | | Preact | 8.2.9 | 3.45kb | The above comparison includes polyfills to support old browsers like IE9 that in Riot.js is supported by default Browsers support Riot is supported by all modern browsers and it does not require any additional polyfill IE 9+ Edge Chrome Safari 7+ Firefox Safari iOS Android Custom tags • Concise syntax • Simple API • Tiny Size Riot brings custom tags to all modern browsers. Think React + Polymer but with enjoyable syntax and a small learning curve. Tag definition ``` javascript Seconds Elapsed: { time } this.time = opts.start || 0 tick() { this.update({ time: ++this.time }) } var timer = setInterval(this.tick, 1000) this.on(unmount, function() { clearInterval(timer) }) ``` Open this example on Plunker Mounting javascript riot.mount(timer, { start: 0 }) Nesting Custom tags lets you build complex views with HTML. html <timetable> <timer start="0"></timer> <timer start="10"></timer> <timer start="20"></timer> </timetable> HTML syntax is the de facto language on the web and its designed for building user interfaces. The syntax is explicit, nesting is inherent to the language and attributes offer a clean way to provide options for custom tags. Expressions Bindings Absolutely the smallest possible amount of DOM updates and reflows. One way data flow: updates and unmounts are propagated downwards from parent to children. Expressions are pre-compiled and cached for high performance. Lifecycle events for more control. Close to standards No proprietary event system. Event normalization. The rendered DOM can be freely manipulated with other tools. No extra HTML root elements or data- attributes. Plays well with any frontend framework. Use your dearest language and tools Create tags with CoffeeScript, Jade, LiveScript, Typescript, ES6 or any pre-processor you want. Integrate with NPM, CommonJS, AMD, Bower or Component Develop with Gulp, Grunt, Wintersmith, webpack*, Rollup*, Browserify*, Babel* or Bublé Test with Karma*, Mocha or whatever you like Note: * officially maintained CDN hosting jsDelivr cdnjs Concise syntax Power shortcuts: class={ enabled: is_enabled, hidden: hasErrors() }. No extra brain load such as render, state, or constructor. Interpolation: Add #{ items.length + 1 } or class="item { selected: flag }" Compact ES6 method syntax. Demos Riot Examples - Communitys Official Riot Animore - Official Tags Animations Library Riot Todo MVC Hackernews reader Vuejs examples by Riotjs Flux-like ES6 Todo Timer Another flux demo comparable to React ones Various experiments Isomorphic application Isomorphic proof of concept flux-riot todo Another Riot Todo MVC Cheft isomorphic by express electron-riot - Riot in an electron application An express, riot, jade, webpack simple boilerplate Riot.js vs React.js comparison of a simple comment box Riot Seed project - webpack, routing, ava tests, dispatcher Riot-Redux League Table example Riot vs React vs Ractive Counters using Redux store Books Building Apps with Riot Tutorials Building Apps with Riot, ES6 and Webpack Building Apps with Riot, Babel, RiotControl and Webpack Building tabs with Riot The "React tutorial" for Riot How to package "tag libraries" in Riot Another React tutorial with Riot Riot Custom Tag by Example Riot Compiler Explained Adding compiled Riot tags to your Gulp + Browserify build The anatomy of a tag - a primer tutorial Using TDD with Riot+mocha+chai The Basics - from ground up to connected tag-networks Hello Riot.js : a quick tutorial about this awesome lib Video Tutorials Introduction Loops, Events and Callbacks Server Rendering with Node & Express Riot And Webpack Setup Riot and Redux - Part 1 Riot and Redux - Part 2 Riot and Redux - Part 3 Riot and Redux - Part 4 Riot and Redux - Part 5 Riot and Redux - Part 6 Libraries / Frameworks Flux- like event controller for Riot flux-riot framework Cheftjs - chinese framework for Riot Veronica - flux adaption for Riot Minimal Flux dispatcher pattern riot-format: a format library for riotjs, like angular $filter riot-view-router: a simple state based router mixin riotx - Centralized State Management for riot.js Components Material UI RiotGear Components RiotGear Router Riot Bootstrap iToolkit Riot Routehandler-(Demo) Riot Flipcard - (Demo) Riot Grid - (Demo) Riot Grid2 - (Demo) Riot Subtag - faster than lots of ifs ESLint Riot Plugin riot-animate Nest UI - (Demo) rGrid - (Demo) Resources create-riot-app dev environment Riot + AngularJS Module loader for WebPack Riot + Meteor Riot Snake Game Riot Tag Syntax Checker Riot 文档中译版 :cn: Riot + Wintersmith Riot precompiler plugin for lineman Riot Startkit - Flux inspired skeleton app + WebPack + PostCSS Yeoman generator - Generator riot mobile Yeoman generator - Generator riot element Riot for TypeScript Riot loader plugin for RequireJS Riot loader plugin for JSPM/SystemJS RiotJS Style Guide Riot Cheatsheet Performance Riot vs React performance: (Riot version) vs (React version) Miscellaneous Q&A with RiotJS author Tero Piirainen riot-detector (Chrome Extension) Editors / Editor Plugins (Syntax highlighting, autcompletion, etc...) riot (Atom Package) language-riot-tag (Atom Package) Based on Vues official Sublime Text highlighter Note: Designed for html, not jade. sublime-tag (Sublime Text) riot-tag (Visual Studio) web-mode (Emacs) See how to configure #1967 How to contribute If you are reading this its already a good sign and we are thankful for it! We try our best working as much as we could on riot but your help is always appreciated. If you want to contribute to riot helping us maintaining the project please check first the list of our open issues to understand whether there is a task where you could help. Riot is mainly developed on UNIX systems so you will be able to run all the commands necessary to build and test the library using our Makefile. If you are on a Microsoft machine it could be harder to set up you development environment properly. Following the steps below you should be able to properly submit your patch to the project 1) Clone the repo and browse to the riot folder shell $ git clone git@github.com:riot/riot.git && cd riot 2) Set up your git branch shell $ git checkout -b feature/my-awesome-patch 3) Install the npm dependencies shell $ npm i 4) Build and test riot using the Makefile ```shell To build and test riot $ make riot To build without testing $ make raw To build anytime you change a src file $ make watch To bench riot $ make perf ``` 5) Pull request only against the dev branch making sure you have read our pull request template 6) Be patient Credits Riot is made with :heart: by many smart people from all over the world. Thanks to all the contributors Its actively maintained by: Gianluca Guarini Official Website http://riot.js.org Backers Support us with a monthly donation and help us continue our activities. Become a backer Sponsors Become a sponsor to get your logo on our README. Become a sponsor Thanks Special thanks to Browserstack for their support