hammer js a javascript library for detecting touch gestures installation npm sh npm install save hammerjs or yarn sh yarn add hammerjs or cdn https cdnjs com libraries hammer js usage hammer js has a quick start option for gestures it already recognizes js get a reference to an element var square document queryselector square create an instance of hammer with the reference var hammer new hammer square subscribe to a quick start event press tap or doubletap for a full list of quick start events read the documentation hammer on press function e e target classlist toggle expand console log youre pressing me console log e if you want to recognize your own gestures such as tripletap then youll have to use these steps js get a reference to an element var square document queryselector square create a manager to manage the element var manager new hammer manager square create a recognizer var tripletap new hammer tap event tripletap taps 3 add the recognizer to the manager manager add tripletap subscribe to the event manager on tripletap function e e target classlist toggle expand console log youre triple tapping me console log e examples tap double tap press swipe documentation for further information regarding hammer js please read our documentation contributions feel encouraged to report issues or submit pull requests when youre ready to do either read our contribution guidelines if youre looking for another form of contribution we love help answering questions on our slack channel license mit examples contributions