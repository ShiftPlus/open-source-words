react howto if youre new to react or frontend in general you may find the ecosystem confusing there are a few reasons for this react has historically been targeted at early adopters and experts facebook only open sources what it actually uses so it doesnt focus on tooling for smaller than facebook projects theres a lot of bad marketing masquerading as react guides throughout this document ill assume youve built a web page with html css and javascript why should you listen to me theres a ton of conflicting advice about react out there why listen to me i was one of the original members of the facebook team that built and open sourced react im no longer at facebook and im now at a small startup so i have a non facebook perspective as well how to tackle the react ecosystem all software is built on a stack of technologies and you need to understand enough of that stack to build your app the reason why the react ecosystem of tooling seems overwhelming is because its always explained in the wrong order you should learn in this order without skipping ahead or learning concurrently react itself npm javascript “bundlers” es6 routing flux you dont need to learn all of these to be productive with react only move to the next step if you have a problem that needs to be solved additionally there are a few topics that are often mentioned in the react community that are bleeding edge the topics below are interesting but theyre difficult to understand are far less popular than the above topics and arent required for most apps inline styles server rendering immutable js relay falcor etc learning react itself its a common misconception that you need to waste a lot of time setting up tooling to start to learn react in the official documentation youll find a copy paste html template that you can save in an html file and get started right away no tooling is required for this step and dont start learning extra tooling until youre comfortable with react basics i still think the easiest way to learn react is the official tutorial learning npm npm is the node js package manager and is the most popular way front end engineers and designers share javascript code it includes a module system called commonjs and lets you install command line tools written in javascript read this post for background on why commonjs is necessary for browsers or the commonjs spec wiki for more on the commonjs api most reusable components libraries and tools in the react ecosystem are available as commonjs modules and are installed with npm learning javascript bundlers for a number of good technical reasons commonjs modules i e everything in npm cannot be used natively in the browser you need a javascript “bundler” to “bundle” these modules into js files that you can include in your web page with a script tag examples of javascript bundlers include webpack and browserify both are good choices but i prefer webpack since it has a lot of features that make development of large apps easier since its documentation can be confusing i have a plug and play template for getting started and i wrote a how to guide for webpack for more complex use cases react also now offers an officially supported cli tool called create react app it lets you create react projects powered by webpack without any configuration it has its limitations but it can serve as a great starting point and its updates will add more features over time it also offers an ejection feature that copies all configs and dependencies into your project so you have full control over them one thing to keep in mind commonjs uses the require function to import modules so a lot of people get confused and think that it has something to do with a project called require js for a number of technical reasons i would suggest that you avoid require js its also not very popular in the react ecosystem learning es6 outside of jsx which you learned in the react tutorial you may see some funny syntax in react examples this is called es6 and its the latest version of javascript so you may not have learned it yet since its so new its not supported in browsers yet but your bundler can translate it for you with the proper configuration if you just want to get things done with react you can skip learning es6 or try to pick it up along the way you may see some talk about es6 classes being the preferred way to create react components this is untrue most people including facebook are using react createclass learning routing “single page applications” are all the rage these days these are web pages that load once and when the user clicks on a link or a button javascript running on the page updates the address bar but the web page is not refreshed management of the address bar is done by something called a router the most popular router in the react ecosystem is react router if youre building a single page application use it unless you have a good reason not to dont use a router if you arent building a single page application most projects start out as smaller components inside of a larger application anyway learning flux youve probably heard of flux theres a ton of misinformation about flux out there a lot of people sit down to build an app and want to define their data model and they think they need to use flux to do it this is the wrong way to adopt flux flux should only be added once many components have already been built react components are arranged in a hierarchy most of the time your data model also follows a hierarchy in these situations flux doesnt buy you much sometimes however your data model is not hierarchical when your react components start to receive props that feel extraneous or you have a small number of components starting to get very complex then you might want to look into flux youll know when you need flux if you arent sure if you need it you dont need it if you have decided to use flux the most popular and well documented flux library is redux there are a lot of alternatives out there and youll be tempted to evaluate lots of them but my advice is to just stick with the most popular one learning inline styles pre react a lot of people reused css styles with complicated style sheets built by preprocessors like sass since react makes writing reusable components easy your stylesheets can be less complicated many in the community including myself are experimenting with getting rid of stylesheets altogether this is a fairly crazy idea for a number of reasons it makes media queries more difficult and its possible that there are performance limitations using this technique when starting out with react just style things the way you normally would once youve got a feel for how react works you can look at alternate techniques one popular one is bem i recommend phasing out your css preprocessor since react gives you a more powerful way to reuse styles by reusing components and your javascript bundler can generate more efficient stylesheets for you i gave a talk about this at oscon with that said react like any other javascript library will work just fine with a css preprocessor alternatively you can also use css modules more specifically react css modules with css modules youll still write css or sass less stylus but you can manage and compose your css files like youd do with inline styles in react and you dont need to worry about managing your class names using methodologies like bem as this will be handled for you under the hood by the module system learning server rendering server rendering is often called universal or isomorphic js it means that you can take your react components and render them to static html on the server this improves initial startup performance because the user does not need to wait for js to download in order to see the initial ui and react can re use the server rendered html so it doesnt need to generate it client side you need server rendering if you notice that your initial render is too slow or if you want to improve your search engine ranking while its true that google now indexes client rendered content as of january 2016 every time its been measured its been shown to negatively affect ranking potentially because of the performance penalty of client side rendering server rendering still requires a lot of tooling to get right since it transparently supports react components written without server rendering in mind you should build your app first and worry about server rendering later you wont need to rewrite all of your components to support it learning immutable js immutable js provides a set of data structures that can help to solve certain performance issues when building react apps its a great library and youll probably use it a lot in your apps moving forward but its completely unnecessary until you have an appreciation of the performance implications learning relay falcor etc these are technologies that help you reduce the number of ajax requests theyre still very cutting edge so if you dont have a problem with too many ajax requests you dont need relay or falcor