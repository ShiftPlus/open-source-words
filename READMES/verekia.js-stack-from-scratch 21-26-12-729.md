javascript stack from scratch welcome to my modern javascript stack tutorial javascript stack from scratch 🎉 this is the v2 of the tutorial major changes happened since the 2016 release check the change log this is a straight to the point guide to assembling a javascript stack it requires some general programming knowledge and javascript basics it focuses on wiring tools together and giving you the simplest possible example for each tool you can see this tutorial as a way to write your own boilerplate from scratch since the goal of this tutorial is to assemble various tools i do not go into details about how these tools work individually refer to their documentation or find other tutorials if you want to acquire deeper knowledge in them you dont need to use this entire stack if you build a simple web page with a few js interactions of course a combination of browserify webpack babel jquery is enough to be able to write es6 code in different files but if you want to build a web app that scales and need help setting things up this tutorial will work great for you a big chunk of the stack described in this tutorial uses react if you are beginning and just want to learn react create react app will get you up and running with a react environment very quickly with a pre made configuration i would for instance recommend this approach to someone who arrives in a team thats using react and needs to catch up with a learning playground in this tutorial you wont use a pre made configuration because i want you to understand everything thats happening under the hood code examples are available for each chapter and you can run them all with yarn yarn start i recommend writing everything from scratch yourself by following the step by step instructions though final code available in the js stack boilerplate repository and in the releases there is a live demo too works on linux macos and windows note since the tutorial was last edited in may 2017 a few libraries have slightly changed their apis 95 of the tutorial is still perfectly valid but if you run into something weird make sure to check out the open issues table of contents 01 node yarn package json 02 babel es6 eslint flow jest husky 03 express nodemon pm2 04 webpack react hmr 05 redux immutable fetch 06 react router server side rendering helmet 07 socket io 08 bootstrap jss 09 travis coveralls heroku coming up next setting up your editor atom first mongodb progressive web app e2e testing translations if you want to add your translation please read the translation recommendations to get started v2 bulgarian by mihailgaberov chinese simplified by yepbug french by naomi hauret italian by fabrizio bertone fbertone it check out the ongoing translations v1 chinese simplified by pd4d10 italian by fabrizio bertone japanese by takahashim russian by react theming thai by microbenz credits created by verekia – verekia com license mit