overview web starter kit is an opinionated boilerplate for web development tools for building a great experience across many devices and performance oriented helping you to stay productive following the best practices outlined in googles web fundamentals a solid starting point for both professionals and newcomers to the industry features feature summary responsive boilerplate a responsive boilerplate optimized for the multi screen web powered by material design lite youre free to use either this or a completely clean slate via basic html sass support compile sass into css with ease bringing support for variables mixins and more run gulp serve or gulp for production performance optimization minify and concatenate javascript css html and images to help keep your pages lean run gulp to create an optimised version of your project to dist code linting javascript code linting is done using eslint a pluggable linter tool for identifying and reporting on patterns in javascript web starter kit uses eslint with eslint config google which tries to follow the google javascript style guide es2015 via babel 6 0 optional es2015 support using babel to enable es2015 support remove the line only gulpfile babel js in the babelrc file es2015 source code will be automatically transpiled to es5 for wide browser support built in http server a built in server for previewing your site locally while you develop and iterate live browser reloading reload the browser in real time anytime an edit is made without the need for an extension run gulp serve and edit your files cross device synchronization synchronize clicks scrolls forms and live reload across multiple devices as you edit your project powered by browsersync run gulp serve and open up the ip provided on other devices on your network offline support thanks to our baked in service worker pre caching sites deploying dist to a https domain will enjoy offline support this is made possible by sw precache pagespeed insights web performance metrics showing how well your site performs on mobile and desktop run gulp pagespeed quickstart download the kit or clone this repository and build on what is included in the app directory there are two html starting points from which you can choose index html the default starting point containing material design layout basic html no layout but still includes our minimal mobile best practices be sure to look over the installation docs to verify your environment is prepared to run wsk once you have verified that your system can run wsk check out the commands available to get started web performance web starter kit strives to give you a high performance starting point out of the box our median web page test scores for the default template have a speed index of 1100 1000 is ideal and a repeat visit speed index of 550 thanks to service worker precaching browser support at present we officially aim to support the last two versions of the following browsers chrome edge firefox safari opera internet explorer 9 this is not to say that web starter kit cannot be used in browsers older than those reflected but merely that our focus will be on ensuring our layouts work great in the above troubleshooting if you find yourself running into issues during installation or running the tools please check our troubleshooting guide and then open an issue we would be happy to discuss how they can be solved a boilerplate only option if you would prefer not to use any of our tooling delete the following files from the project package json gulpfile babel js and travis yml you can now safely use the boilerplate with an alternative build system or no build system at all if you choose docs and recipes file appendix what do the different files here do using material design lites sass how to get mdls sass working with wsk deployment guides available for firebase google app engine and other services gulp recipes the official gulp recipes directory includes a comprehensive list of guides for different workflows you can add to your project inspiration web starter kit is inspired by mobile html5 boilerplate and yeomans generator gulp webapp having taken input from contributors to both projects during development our faqs attempt to answer commonly asked questions about the project contributing contributions questions and comments are all welcome and encouraged for code contributions to web starter kit please see our contribution guide before submitting a pull request website related issues should be filed on the web fundamentals issue tracker license apache 2 0 copyright 2015 google inc