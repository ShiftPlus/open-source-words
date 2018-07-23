Redux DevTools A live-editing time travel environment for Redux. See Dans React Europe talk demoing it! Note that the implemention in this repository is different from Redux DevTools Extension. Please refer to the latter for browser extension. Table of Contents Features Overview Browser Extension Setup Instructions Custom Monitors License Features Lets you inspect every state and action payload Lets you go back in time by “cancelling” actions If you change the reducer code, each “staged” action will be re-evaluated If the reducers throw, you will see during which action this happened, and what the error was With persistState() store enhancer, you can persist debug sessions across page reloads Overview Redux DevTools is a development time package that provides power-ups for your Redux development workflow. Be careful to strip its code in production (see walkthrough for instructions)! To use Redux DevTools, you need to choose a “monitor”—a React component that will serve as a UI for the DevTools. Different tasks and workflows require different UIs, so Redux DevTools is built to be flexible in this regard. We recommend using LogMonitor for inspecting the state and time travel, and wrap it in a DockMonitor to quickly move it across the screen. That said, when youre comfortable rolling up your own setup, feel free to do this, and share it with us. If you came here looking for what do the “Reset”, “Revert”, “Sweep” or “Commit” buttons do, check out the LogMonitor documentation. Browser Extension If you dont want to bother with installing Redux DevTools and integrating it into your project, consider using Redux DevTools Extension for Chrome and Firefox. It provides access to the most popular monitors, is easy to configure to filter actions, and doesnt require installing any packages. Setup Instructions Read the installation walkthrough for integration instructions and usage examples (<DevTools> component, DevTools.instrument(), exclude from production builds, gotchas). Running Examples Clone the project: git clone https://github.com/gaearon/redux-devtools.git cd redux-devtools Run npm install in the root folder: npm install Now you can open an example folder and run npm install there: cd examples/counter # or examples/todomvc npm install Finally, run the development server and open the page: npm start open http://localhost:3000 Try clicking on actions in the log, or changing some code inside the reducers. You should see the action log re-evaluate the state on every code change. Also try opening http://localhost:3000/?debug_session=123, click around, and then refresh. You should see that all actions have been restored from the local storage. Custom Monitors DevTools accepts monitor components so you can build a completely custom UI. LogMonitor and DockMonitor are just examples of what is possible. I challenge you to build a custom monitor for Redux DevTools! Some crazy ideas for custom monitors: A slider that lets you jump between computed states just by dragging it An in-app layer that shows the last N states right in the app (e.g. for animation) A time machine like interface where the last N states of your app reside on different Z layers Feel free to come up with and implement your own! Check LogMonitor propTypes to see what you can do. In fact some of these are implemented already: Slider Monitor Inspector Diff Monitor Filterable Log Monitor Chart Monitor Filter Actions (Does not have a UI but can wrap any other monitor) Dispatch Keep them coming! Create a PR to add your custom monitor. License MIT