deprecation warning this project was started at the advent of the redux ecosystem and was intended to help users get up and running quickly since then tooling and best practices have evolved tremendously in order to get the most modern experience possible i recommend checking out something like create react app which is supported by many core react and redux developers you are welcome to use this project if it is a better fit for your needs but if you are brand new to the ecosystem i highly recommend checking out something that has received more recent updates thank you to everyone who made this project possible over the past year s react redux starter kit this starter kit is designed to get you up and running with a bunch of awesome front end technologies the primary goal of this project is to provide a stable foundation upon which to build modern web appliications its purpose is not to dictate your project structure or to demonstrate a complete real world application but to provide a set of tools intended to make front end development robust easy and most importantly fun check out the full feature list below finally this project wouldnt be possible without the help of our many contributors what you see today is the product of hundreds changes made to keep up with an ever evolving ecosystem thank you for all of your help table of contents requirements installation running the project project structure live development hot reloading redux devtools routing testing dirty chai building for production deployment thank you requirements node 5 0 0 yarn 0 23 0 or npm 3 0 0 installation after confirming that your environment meets the above requirements you can create a new project based on react redux starter kit by doing the following bash git clone https github com davezuko react redux starter kit git my project name cd my project name when thats done install the project dependencies it is recommended that you use yarn for deterministic dependency management but npm install will suffice bash yarn install project dependencies or npm install running the project after completing the installation step youre ready to start the project bash yarn start start the development server or npm start while developing you will probably rely mostly on yarn start however there are additional scripts at your disposal yarn script description start serves your app at localhost 3000 build builds the application to dist test runs unit tests with karma see testing test watch runs test in watch mode to re run tests when changed lint lints the project for potential errors lint fix lints the project and fixes all correctable errors project structure the project structure presented in this boilerplate is fractal where functionality is grouped primarily by feature rather than file type this structure is only meant to serve as a guide it is by no means prescriptive that said it aims to represent generally accepted guidelines and patterns for building scalable applications if you wish to read more about this pattern please check out this awesome writeup by justin greenberg ├── build all build related code ├── public static public assets not imported anywhere in source code ├── server express application that provides webpack middleware │ └── main js server application entry point ├── src application source code │ ├── index html main html page container for app │ ├── main js application bootstrap and rendering │ ├── normalize js browser normalization and polyfills │ ├── components global reusable components │ ├── containers global reusable container components │ ├── layouts components that dictate major page structure │ │ └── pagelayout global application layout in which to render routes │ ├── routes main route definitions and async split points │ │ ├── index js bootstrap main application routes with store │ │ ├── home fractal route │ │ │ ├── index js route definitions and async split points │ │ │ ├── assets assets required to render components │ │ │ ├── components presentational react components │ │ │ └── routes fractal sub routes optional │ │ └── counter fractal route │ │ ├── index js counter route definition │ │ ├── container connect components to actions and store │ │ ├── modules collections of reducers constants actions │ │ └── routes fractal sub routes optional │ ├── store redux specific pieces │ │ ├── createstore js create and instrument redux store │ │ └── reducers js reducer registry and injection │ └── styles application wide styles generally settings └── tests unit tests live development hot reloading hot reloading is enabled by default when the application is running in development mode yarn start this feature is implemented with webpacks hot module replacement capabilities where code updates can be injected to the application while its running no full reload required heres how it works for javascript modules a code change will trigger the application to re render from the top of the tree global state is preserved i e redux but any local component state is reset this differs from react hot loader but weve found that performing a full re render helps avoid subtle bugs caused by rhl patching for sass any change will update the styles in realtime no additional configuration or reload needed redux devtools we recommend using the redux devtools chrome extension using the chrome extension allows your monitors to run on a separate thread and affords better performance and functionality it comes with several of the most popular monitors is easy to configure filters actions and doesnt require installing any packages in your project however its easy to bundle these developer tools locally should you choose to do so first grab the packages from npm bash yarn add dev redux devtools redux devtools log monitor redux devtools dock monitor then follow the manual integration walkthrough routing we use react router route definitions route index js to define units of logic within our application see the project structure section for more information testing to add a unit test create a spec js file anywhere inside of tests karma and webpack will automatically find these files and mocha and chai will be available within your test without the need to import them here are a few important plugins and packages available to you during testing dirty chai some of the assertions available from chai use magical getters these are problematic for a few reasons 1 if you mistype a property name e g expect false to be tru then the expression evaluates to undefined the magical getter on the true is never run and so your test silently passes 2 by default linters dont understand them and therefore mark them as unused expressions which can be annoying dirty chai fixes this by converting these getters into callable functions this way if mistype an assertion our attempt to invoke it will throw due to the property being undefined js this silently passes because the getter ontrue is never invoked it should be true expect false to be tru evalutes to undefined much better our assertion is invalid so it throws rather than implicitly passing it should be true expect false to be tru tru is not defined building for production deployment out of the box this starter kit is deployable by serving the dist folder generated by yarn build this project does not concern itself with the details of server side rendering or api structure since that demands a more opinionated structure that makes it difficult to extend the starter kit the simplest deployment strategy is a static deployment static deployments serve the application with a web server such as nginx by pointing it at your dist folder make sure to direct incoming route requests to the root dist index html file so that the client application will be loaded react router will take care of the rest if you are unsure of how to do this you might find this documentation helpful the express server that comes with the starter kit is able to be extended to serve as an api and more but is not required for a static deployment thank you this project wouldnt be possible without help from the community so id like to highlight some of its biggest contributors thank you all for your hard work youve made my life a lot easier and taught me a lot in the process justin greenberg for all of your prs getting us to babel 6 and constant work improving our patterns roman pearah for your bug reports help in triaging issues and pr contributions spencer dixon for your creation of redux cli jonas matser for your help in triaging issues and unending support in our gitter channel and to everyone else who has contributed even if you are not listed here your work is appreciated