overview lets face it forms are really verbose in react to make matters worse most form helpers do wayyyy too much magic and often have a significant performance cost associated with them formik is a small library that helps you with the 3 most annoying parts getting values in and out of form state validation and error messages handling form submission by colocating all of the above in one place formik will keep things organized making testing refactoring and reasoning about your forms a breeze developer experience i jaredpalmer wrote formik while building a large internal administrative dashboard with eonwhite with around 30 unique forms it quickly became obvious that we could benefit by standardizing not just our input components but also the way in which data flowed through our forms why not redux form by now you might be thinking why didnt you just use redux form good question according to our prophet dan abramov form state is inherently ephemeral and local so tracking it in redux or any kind of flux library is unnecessary redux form calls your entire top level redux reducer multiple times on every single keystroke this is fine for small apps but as your redux app grows input latency will continue to increase if you use redux form redux form is 22 5 kb minified gzipped formik is 7 8 kb my goal with formik was to create a scalable performant form helper with a minimal api that does the really really annoying stuff and leaves the rest up to you testimonials i cant believe people ever put forms in redux or did anything else other than this james long creator of prettier and actual budget formik all day all long ken wheeler director of open source at formidable labs been using jaredpalmers formik lately at work – this is my all time favorite way to handle forms brent jackson creator of rebass styled system compositor and many more formik removes most of the moving parts involved in forms allowing me to move faster with more confidence kye hohenberger creator of emotion influences formik started by expanding on this little higher order component by brent jackson some naming conventions from redux form and most recently the render props approach popularized by react motion and react router 4 whether you have used any of the above or not formik only takes a few minutes to get started with installation add formik to your project version 1 0 is coming will be released by the end of july so i suggest installing from the next release channel bash npm i formik next save you can also try before you buy with this demo of formik on codesandbox io demos basics sync validation building your own input primitives working with 3rd party inputs 1 react select working with 3rd party inputs 2 draft js accessing react lifecycle functions talks an introduction to formik by jared palmer spotify nyc august 15th 2017 community articles tutorials better react forms with formik the joy of forms with react and formik painless react forms with formik the gist formik keeps track of your forms state and then exposes it plus a few reusable methods and event handlers handlechange handleblur and handlesubmit to your form via props handlechange and handleblur work exactly as expected they use a name or id attribute to figure out which field to update there are two ways to use formik withformik a higher order component hoc that accepts a configuration object formik a react component with a render prop both do exactly the same thing and share the same internal implementation they just differ in their respective style js higher order component import react from react import withformik from formik our inner form component which receives our forms state and updater methods as props const innerform values errors touched handlechange handleblur handlesubmit issubmitting touched email errors email errors email touched password errors password errors password submit wrap our form with the using withformik hoc const myform withformik transform outer props into form values mappropstovalues props email password add a custom validation function this can be async too validate values props const errors if values email errors email required else if a z0 9 a z0 9 a z 2 4 i test values email errors email invalid email address return errors submission handler handlesubmit values props setsubmitting seterrors setvalues setstatus and other goodies logintomyapp values then user setsubmitting false do whatevs props updateuser user errors setsubmitting false maybe even transform your apis errors into the same shape as formiks seterrors transformmyapierrors errors innerform use anywhere const basic my form this can be anywhere in your application export default basic js render prop import react from react import formik from formik const basic my form this can be anywhere in your application the benefit of the render prop approach is that you have full access to reacts state props and composition model thus there is no need to map outer props to values you can just set the initial values and if they depend on props state then boom you can directly access to props state the render prop accepts your inner form component which you can define separately or inline totally up to you formik render props form form formik component innerform formik props form form formik identical to as render just written differently formik initialvalues email password validate values same as above but feel free to move this into a class method now let errors if values email errors email required else if a z0 9 a z0 9 \ a z 2 4 i test values email errors email invalid email address return errors onsubmit values setsubmitting seterrors setvalues and other goodies logintomyapp values then user setsubmitting false do whatevs props updateuser user errors setsubmitting false maybe transform your apis errors into the same shape as formiks seterrors transformmyapierrors errors render values errors touched handlechange handleblur handlesubmit issubmitting form onsubmit handlesubmit input type email name email onchange handlechange onblur handleblur value values email touched email errors email div errors email div input type password name password onchange handlechange onblur handleblur value values password touched password errors password div errors password div button type submit disabled issubmitting submit button form export default basic complementary packages as you can see above validation is left up to you feel free to write your own validators or use a 3rd party library personally i use yup for object schema validation it has an api thats pretty similar joi react proptypes but is small enough for the browser and fast enough for runtime usage because i heart yup sooo much formik has a special config option prop for yup called validationschema which will automatically transform yups validation errors into a pretty object whose keys match values and touched anyways you can install yup from npm npm install yup save table of contents start doctoc generated toc please keep comment here to allow auto update dont edit this section instead re run doctoc to update dont edit this section instead re run doctoc to update guides basics react native why use setfieldvalue instead of handlechange avoiding new functions in render using formik with typescript render props formik and field withformik api formik formik render methods formik props dirty boolean errors field string string handleblur e any void handlechange e react changeevent any void handlereset void handlesubmit e react formevent htmlformevent void issubmitting boolean isvalid boolean resetform nextvalues values void seterrors fields field string string void setfielderror field string errormsg string void setfieldtouched field string istouched boolean shouldvalidate boolean void submitform void submitcount number setfieldvalue field string value any shouldvalidate boolean void setstatus status any void setsubmitting issubmitting boolean void settouched fields field string boolean void setvalues fields field string any void status any touched field string boolean values field string any validateform values any void validatefield field string void component render props formikprops values reactnode children func enablereinitialize boolean isinitialvalid boolean initialvalues values onreset values values formikbag formikbag void onsubmit values values formikbag formikbag void validate values values formikerrors values promise any validateonblur boolean validateonchange boolean validationschema schema schema field validate value any undefined string promise any refs fieldarray name string validateonchange boolean fieldarray array of objects fieldarray validation gotchas fieldarray helpers fieldarray render methods render arrayhelpers arrayhelpers react reactnode component react reactnode form withformik options options displayname string enablereinitialize boolean handlesubmit values values formikbag formikbag void the formikbag isinitialvalid boolean props props boolean mappropstovalues props props values validate values values props props formikerrors values promise any validateonblur boolean validateonchange boolean validationschema schema props props schema injected props and methods organizations and projects using formik authors contributors end doctoc generated toc please keep comment here to allow auto update guides basics imagine you want to build a form that lets you edit user data however your user api has nested objects like so js id string email string social facebook string twitter string when we are done we want our dialog to accept just a user updateuser and onclose props js user js import react from react import dialog from mysuperdialog import formik from formik const edituserdialog user updateuser onclose return edit user callmyapi user id values then updateduser actions setsubmitting false updateuser updateduser onclose error actions setsubmitting false actions seterrors transformmyapierrortoanobject error render values errors touched handleblur handlechange handlesubmit issubmitting errors email touched email errors email errors social errors social facebook touched facebook errors social facebook errors social errors social twitter touched twitter errors social twitter submit to make writing forms less verbose formik comes with a few helpers to save you key strokes field form this is the exact same form as before but written with form and field js edituserdialog js import react from react import dialog from mysuperdialog import formik field form from formik const edituserdialog user updateuser onclose return edit user callmyapi user id values then updateduser actions setsubmitting false updateuser updateduser onclose error actions setsubmitting false actions seterrors transformmyapierrortoanobject error render errors touched issubmitting errors email touched social email errors email errors social facebook touched social facebook errors social facebook errors social twitter touched social twitter errors social twitter submit react native formik is 100 compatible with react native and react native web however because of differences between reactdoms and react natives handling of forms and text input there are two differences to be aware of this section will walk you through them and what i consider to be best practices before going any further heres a super minimal gist of how to use formik with react native that demonstrates the key differences js formik x react native example import react from react import button textinput view from react native import withformik from formik const enhancer withformik const myreactnativeform props props setfieldvalue email text value props values email export default enhancer myreactnativeform as you can see above the notable differences between using formik with react dom and react native are formiks props handlesubmit is passed to a button onpress instead of html form onsubmit component since there is no form element in react native textinput uses formiks props setfieldvalue instead of props handlechange to understand why see the discussion below why use setfieldvalue instead of handlechange cuz handlechange will not work in react native js import button textinput view from react native import formik from formik const myreactnativeform props settimeout console log json stringify values null 2 actions setsubmitting false 1000 render formikprops the reason is that formiks handlechange function expects its first argument to be synthetic dom event where the event target is the dom input element and event target id or event target name matches the field to be updated without this handlechange will do nothing in react native neither textinput s onchange nor onchangetext callbacks pass such an event or one like it to its callback instead they do the following emphasis added onchange function\ callback that is called when the text inputs text changes onchangetext function\ callback that is called when the text inputs text changes changed text is passed as an argument to the callback handler however formik works just fine if you use props setfieldvalue philosophically just treat react natives textinput the same way you would any other 3rd party custom input element in conclusion the following will work in react native js this works export const myreactnativeform props view textinput onchangetext text props setfieldvalue email text value props values email button onpress props handlesubmit view avoiding new functions in render if for any reason you wish to avoid creating new functions on each render i suggest treating react natives textinput as if it were another 3rd party custom input element write your own class wrapper around the custom input element pass the custom component props setfieldvalue setfieldvalue instead of props handlechange handlechange use a custom change handler callback that calls whatever you passed in setfieldvalue as in this case well match the react native textinput api and call it this props onchangetext for parity js formikreactnativetextinput js import as react from react import textinput from react native export default class formikreactnativetextinput extends react component handlechange value string remember that onchangetext will be formiks setfieldvalue this props onchangetext this props name value render we want to pass through all the props except for onchangetext const onchangetext otherprops this props return then you could just use this custom input as follows tsx myreactnativeform js import view button from react native import textinput from formikreactnativetextinput import formik from formik const myreactnativeform props settimeout console log json stringify values null 2 actions setsubmitting false 1000 render props export default myreactnativeform using formik with typescript the formik source code is written in typescript so you can rest assured that types will always be up to date as a mental model formiks types are very similar to react router 4s route render props formik and field tsx import as react from react import formik formikprops form field fieldprops from formik interface myformvalues firstname string export const myapp react sfc whatever return my example alert json stringify values render formikbag formikprops form touched firstname form errors firstname form errors firstname withformik tsx import react from react import as yup from yup import withformik formikprops formikerrors form field from formik shape of form values interface formvalues email string password string interface otherprops message string you may see user injectedformikprops instead of what comes below they are the same injectedformikprops was artifact of when formik only exported an hoc it is also less flexible as it must wrap all props it passes them through const innerform props otherprops formikprops const touched errors issubmitting message props return message touched email errors email errors email field type password name password touched password errors password div errors password div button type submit disabled issubmitting submit button form the type of props myform receives interface myformprops initialemail string message string if this passed all the way through you might do this or make a union type wrap our form with the using withformik hoc const myform withformik transform outer props into form values mappropstovalues props return email props initialemail password add a custom validation function this can be async too validate values formvalues let errors formikerrors if values email errors email required else if isvalidemail values email errors email invalid email address return errors handlesubmit values do submitting things innerform use anywhere const basic my app this can be anywhere in your application export default basic api formik formik is a component that helps you with building forms it uses a render props pattern made popular by libraries like react motion and react router js import react from react import formik from formik const basicexample my form settimeout alert json stringify values null 2 actions setsubmitting false 1000 render props props errors name props errors name submit formik render methods there are three ways to render things with formik formik component formik render formik children formik props all three render methods will be passed the same props dirty boolean returns true if values are not deeply equal from initial values false otherwise dirty is a readonly computed property and should not be mutated directly errors field string string form validation errors should match the shape of your forms values defined in initialvalues if you are using validationschema which you should be keys and shape will match your schema exactly internally formik transforms raw yup validation errors on your behalf if you are using validate then that function will determine the errors objects shape handleblur e any void onblur event handler useful for when you need to track whether an input has been touched or not this should be passed to input onblur handleblur dom only use setfieldtouched in react native handlechange e react changeevent any void general input change event handler this will update the values key where key is the event emitting inputs name attribute if the name attribute is not present handlechange will look for an inputs id attribute note input here means all html inputs dom only use setfieldvalue in react native handlereset void reset handler will reset the form to its initial state this should be passed to button onclick handlereset button handlesubmit e react formevent htmlformevent void submit handler this should be passed to form onsubmit props handlesubmit form issubmitting boolean submitting state either true or false formik will set this to true on your behalf before calling handlesubmit to reduce boilerplate isvalid boolean returns true if the there are no errors or the result of isinitialvalid the form if is in pristine condition i e not dirty resetform nextvalues values void imperatively reset the form this will clear errors and touched set issubmitting to false and rerun mappropstovalues with the current wrappedcomponents props or whats passed as an argument the latter is useful for calling resetform within componentwillreceiveprops seterrors fields field string string void set errors imperatively setfielderror field string errormsg string void set the error message of a field imperatively field should match the key of errors you wish to update useful for creating custom input error handlers setfieldtouched field string istouched boolean shouldvalidate boolean void set the touched state of a field imperatively field should match the key of touched you wish to update useful for creating custom input blur handlers calling this method will trigger validation to run if validateonblur is set to true which it is by default you can also explicitly prevent skip validation by passing a third argument as false submitform void trigger a form submission submitcount number number of times user tried to submit the form increases when handlesubmit is called resets after calling handlereset submitcount is readonly computed property and should not be mutated directly setfieldvalue field string value any shouldvalidate boolean void set the value of a field imperatively field should match the key of values you wish to update useful for creating custom input change handlers calling this will trigger validation to run if validateonchange is set to true which it is by default you can also explicitly prevent skip validation by passing a third argument as false setstatus status any void set a top level status to anything you want imperatively useful for controlling arbitrary top level state related to your form for example you can use it to pass api responses back into your component in handlesubmit setsubmitting issubmitting boolean void set issubmitting imperatively settouched fields field string boolean void set touched imperatively setvalues fields field string any void set values imperatively status any a top level status object that you can use to represent form state that cant otherwise be expressed stored with other methods this is useful for capturing and passing through api responses to your inner component status should only be modifed by calling setstatus status any void touched field string boolean touched fields each key corresponds to a field that has been touched visited values field string any your forms values will have the shape of the result of mappropstovalues if specified or all props that are not functions passed to your wrapped component validateform values any void imperatively call your validate or validateschema depending on what was specified you can optionally pass values to validate against and this modify formik state accordingly otherwise this will use the current values of the form validatefield field string void imperatively call fields validate function if specified for given field formik will use the current field value component tsx const contactform handlesubmit handlechange handleblur values errors errors name errors name submit warning formik component takes precendence over formik render so dont use both in the same formik render props formikprops values reactnode tsx errors name errors name submit children func tsx or handlesubmit handlechange handleblur values errors errors name errors name submit enablereinitialize boolean default is false control whether formik should reset the form if initialvalues changes using deep equality isinitialvalid boolean default is false control the initial value of isvalid prop prior to mount you can also pass a function useful for situations when you want to enable disable a submit and reset buttons on initial mount initialvalues values initial field values of the form formik will make these values available to render methods component as props values values even if your form is empty by default you must initialize all fields with initial values otherwise react will throw an error saying that you have changed an input from uncontrolled to controlled note initialvalues not available to the higher order component use mappropstovalues instead onreset values values formikbag formikbag void your optional form reset handler it is passed your forms values and the formikbag onsubmit values values formikbag formikbag void your form submission handler it is passed your forms values and the formikbag which includes an object containing a subset of the injected props and methods i e all the methods with names that start with set thing resetform and any props that were passed to the the wrapped component note errors touched status and all event handlers are not included in the formikbag validate values values formikerrors values promise any note i suggest using validationschema and yup for validation however validate is a dependency free straightforward way to validate your forms validate the forms values with function this function can either be synchronous and return an errors object js synchronous validation const validate values props let errors if values email errors email required else if a z0 9 a z0 9 a z 2 4 i test values email errors email invalid email address return errors asynchronous and return a promise thats error in an errors object js async validation const sleep ms new promise resolve settimeout resolve ms const validate values props return sleep 2000 then let errors if admin null god includes values username errors username nice try if object keys errors length throw errors validateonblur boolean default is true use this option to run validations on blur events more specifically when either handleblur setfieldtouched or settouched are called validateonchange boolean default is true use this option to tell formik to run validations on change events and change related methods more specifically when either handlechange setfieldvalue or setvalues are called validationschema schema schema a yup schema or a function that returns a yup schema this is used for validation errors are mapped by key to the inner components errors its keys should match those of values field field will automagically hook up inputs to formik it uses the name attribute to match up with formik state field will default to an input element to change the underlying element of field specify a component prop it can either be a string like select or another react component field can also take a render prop js import react from react import formik field from formik const example my form settimeout alert json stringify values null 2 actions setsubmitting false 1000 render props formikprops red green blue submit const custominputcomponent react sfc fieldprops custominputprops field name value onchange onblur form touched errors also values setxxxx handlexxxx dirty isvalid status etc props touched field name errors field name errors field name validate value any undefined string promise any you can run independent field level validations by passing a function to the validate prop the function will respect the validateonblur and validateonchange config props specified in the field s parent formik withformik this function can be either be synchronous and if invalid return a string containing the error message or return undefined js synchronous validation for field const validate value let errormessage if a z0 9 a z0 9 \ a z 2 4 i test value errormessage invalid email address return errormessage async return a promise that throws a string containing the error message this works like formiks validate but instead of returning an errors object its just a string asynchronous and return a promise thats error is an string with the error message js async validation for field const sleep ms new promise resolve settimeout resolve ms const validate value return sleep 2000 then if admin null god includes value throw nice try note to allow for i18n libraries the typescript typings for validate are slightly relaxed and allow you to return a function e g i18n invalid refs when you are not using a custom component and you need to access the underlying dom node created by field e g to call focus pass the callback to the innerref prop instead fieldarray fieldarray is a component that helps with common array list manipulations you pass it a name property with the path to the key within values that holds the relevant array fieldarray will then give you access to array helper methods via render props for convenience calling these methods will trigger validation and also manage touched for you jsx import react from react import formik form field fieldarray from formik here is an example of a form with an editable list next to each input are buttons for insert and remove if the list is empty there is a button to add an item export const friendlist friend list settimeout alert json stringify values null 2 500 render values values friends values friends length 0 values friends map friend index friends index arrayhelpers remove index remove a friend from the list arrayhelpers insert index insert an empty string at a position arrayhelpers push show this when user has removed all friends from the list add a friend submit name string the name or path to the relevant key in values validateonchange boolean default is true determines if form validation should or should not be run after any array manipulations fieldarray array of objects you can also iterate through an array of objects by following a convention of object index property or object index property for the name attributes of field or input elements in fieldarray js form fieldarray name friends render arrayhelpers div values friends map friend index div key index field name friends index name field name friends index age both these conventions do the same button type button onclick arrayhelpers remove index button div button type button onclick arrayhelpers push name age button div form fieldarray validation gotchas validation can be tricky with fieldarray if you use validationschema and your form has array validation requirements like a min length as well as nested array field requirements displaying errors can be tricky formik yup will show validation errors inside out for example js const schema yup object shape friends yup array of yup object shape name yup string min 4 too short required required these constraints take precedence salary yup string min 3 cmon required required these constraints take precedence required must have friends these constraints are shown if and only if inner constraints are satisfied min 3 minimum of 3 friends since yup and your custom validation function should always output error messages as strings youll need to sniff whether your nested error is an array or a string when you go to display it so to display must have friends and minimum of 3 friends our examples array validation contstraints bad js within a fieldarray s render const friendarrayerrors errors errors friends div errors friends div null app will crash good js within a fieldarray s render const friendarrayerrors errors typeof errors friends string div errors friends div null for the nested field errors you should assume that no part of the object is defined unless youve checked for it thus you may want to do yourself a favor and make a custom errormessage component that looks like this js import field getin from formik const errormessage name const error getin form errors name const touch getin form touched name return touch error error null usage null too short or required note in formik v0 12 1 0 a new meta prop may be be added to field and fieldarray that will give you relevant metadata such as error touch which will save you from having to use formik or lodashs getin or checking if the path is defined on your own fieldarray helpers the following methods are made available via render props push obj any void add a value to the end of an array swap indexa number indexb number void swap two values in an array move from number to number void move an element in an array to another index insert index number value any void insert an element at a given index into the array unshift value any number add an element to the beginning of an array and return its length remove t index number t undefined remove an element at an index of an array and return it pop t t undefined remove and return value from the end of the array fieldarray render methods there are three ways to render things with fieldarray fieldarray name component fieldarray name render render arrayhelpers arrayhelpers react reactnode jsx import react from react import formik form field fieldarray from formik export const friendlist friend list use these however you want component react reactnode jsx import react from react import formik form field fieldarray from formik export const friendlist friend list in addition to the array helpers formik state and helpers values touched setxxx etc are provided through a form prop export const mydynamicform move swap push insert unshift pop form whatever you need to do form like field form is a helper component you can use to save time it is tiny wrapper around form onsubmit context formik handlesubmit this means you dont need to explictly type out form onsubmit props handlesubmit if you dont want to reactdom only jsx import react from react import formik field form from formik const example my form settimeout alert json stringify values null 2 actions setsubmitting false 1000 component myform const myform red green blue submit withformik options create a higher order react component class that passes props and form handlers the formikbag into your component derived from supplied options options displayname string when your inner form component is a stateless functional component you can use the displayname option to give the component a proper name so you can more easily find it in react devtools if specified your wrapped form will show up as formik displayname if omitted it will show up as formik component this option is not required for class components e g class xxxxx extends react component enablereinitialize boolean default is false control whether formik should reset the form if the wrapped component props change using deep equality handlesubmit values values formikbag formikbag void your form submission handler it is passed your forms values and the formikbag which includes an object containing a subset of the injected props and methods i e all the methods with names that start with set thing resetform and any props that were passed to the the wrapped component the formikbag props props passed to the wrapped component resetform seterrors setfielderror setfieldtouched setfieldvalue setstatus setsubmitting settouched setvalues note errors touched status and all event handlers are not included in the formikbag isinitialvalid boolean props props boolean default is false control the initial value of isvalid prop prior to mount you can also pass a function useful for situations when you want to enable disable a submit and reset buttons on initial mount mappropstovalues props props values if this option is specified then formik will transfer its results into updatable form state and make these values available to the new component as props values values if mappropstovalues is not specified then formik will map all props that are not functions to the inner components props values values that is if you omit it formik will only pass props where typeof props k function where k is some key even if your form is not receiving any props from its parent use mappropstovalues to initialize your forms empty state validate values values props props formikerrors values promise any note i suggest using validationschema and yup for validation however validate is a dependency free straightforward way to validate your forms validate the forms values with function this function can either be synchronous and return an errors object js synchronous validation const validate values props let errors if values email errors email required else if a z0 9 a z0 9 a z 2 4 i test values email errors email invalid email address return errors asynchronous and return a promise thats error is an errors object js async validation const sleep ms new promise resolve settimeout resolve ms const validate values props return sleep 2000 then let errors if admin null god includes values username errors username nice try if object keys errors length throw errors validateonblur boolean default is true use this option to run validations on blur events more specifically when either handleblur setfieldtouched or settouched are called validateonchange boolean default is true use this option to tell formik to run validations on change events and change related methods more specifically when either handlechange setfieldvalue or setvalues are called validationschema schema props props schema a yup schema or a function that returns a yup schema this is used for validation errors are mapped by key to the inner components errors its keys should match those of values injected props and methods these are identical to the props of formik render props organizations and projects using formik list of organizations and projects using formik authors jared palmer jaredpalmer ian white eonwhite contributors formik is made with 3 thanks to these wonderful people emoji key all contributors list start do not remove or modify this section jared palmer💬 💻 🎨 📖 💡 🤔 👀 ⚠️ ian white💬 🐛 💻 📖 🤔 👀 andrej badin💬 🐛 📖 adam howard💬 🐛 🤔 👀 vlad shcherbin💬 🐛 🤔 brikou carre🐛 📖 sam kvale🐛 💻 ⚠️ jon tansey🐛 💻 tyler martinez🐛 📖 all contributors list end this project follows the all contributors specification contributions of any kind welcome mit license