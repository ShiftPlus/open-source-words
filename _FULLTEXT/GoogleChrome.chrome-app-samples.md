Chrome Apps samples Official samples for Chrome Apps platform. If you want to learn about the platform, you can: look at the source code of the samples below. Most samples have a "Try it now" button that allows you to install and play with it. read the official docs follow the official Codelab presented at Google I/O If you have questions, search or ask at StackOverflow (observe the google-chrome-app tag) or join the Chromium Apps Google group. Samples sample_table_autogen_start THIS TABLE IS AUTOGENERATED! PLEASE, DONT EDIT IT DIRECTLY! Sample | API or feature | Link --- | --- |:---: analytics | storage ios android | appengine-channelapi/app | webview | appsquare | geolocation identity storage | appview/embedded-app | getUserMedia | appview/host-app | appview | blink1 | hid usb | bluetooth-samples/battery-service-demo | bluetooth | bluetooth-samples/device-info-demo | bluetooth | bluetooth-samples/heart-rate-sensor | bluetooth | calculator | clipboard ios android | camera-capture | getUserMedia | clock | framelessWindows geolocation richNotifications storage | context-menu | contextMenu | dart | dart ios | desktop-capture | desktopCapture | dialog-element | | diff | clipboard fileSystem storage | filesystem-access | fileSystem storage | frameless-window | framelessWindows | gcm-notifications | gcm richNotifications storage | gdrive | framelessWindows identity | github-auth | identity | hello-world | ios android | hello-world-sync | storage ios android | hid | hid | identity | identity android | image-edit | fileSystem storage | instagram-auth | identity | io2012-presentation | framelessWindows getUserMedia serial storage webview | - io2012-presentation/helloworld | | - io2012-presentation/servo | getUserMedia serial | - ioio | bluetooth | keyboard-handler | | managed-in-app-payments | in-app-payments | - manga-cam | framelessWindows getUserMedia syncFileSystem | mdns-browser | framelessWindows sockets systemInfo | media-gallery | mediaGallery | messaging/app1 | messaging | messaging/app2 | messaging | messaging/extension | messaging richNotifications | mini-code-edit | commands contextMenu fileSystem | multicast | framelessWindows messaging sockets storage | one-time-payment | identity storage | optional-permissions | optionalPermissions | parrot-ar-drone | old_sockets sockets android | platform-title | framelessWindows | printing | print storage systemInfo | restarted-demo | storage ios | rich-notifications | richNotifications android | sandbox | sandbox | sandboxed-content | sandbox | serial-control-signals | serial | serial/adkjs/app | serial | serial/espruino | serial | serial/ledtoggle | serial | servo | getUserMedia serial | storage | | syncfs-editor | syncFileSystem | systemInfo | systemInfo | tasks | identity android | tcpserver | sockets systemInfo webview | telnet | sockets | text-editor | clipboard fileSystem | todomvc | alarms fileSystem richNotifications storage syncFileSystem android | - tts | tts | - udp | sockets ios | url-handler | storage webview | usb-label-printer | fileSystem getUserMedia optionalPermissions usb | usb/device-info | usb | usb/knob | optionalPermissions usb | weather | geolocation storage ios | web-store | fileSystem identity storage webstore | webgl-pointer-lock | framelessWindows pointerLock | webserver | sockets systemInfo android | websocket-server | sockets ios | webview-samples/browser | webview | webview-samples/declarative-web-request | storage webview | webview-samples/insert-css | storage webview | webview-samples/local-resources | webview | webview-samples/multi-tab-browser | contextMenu webview | webview-samples/new-window | webview | webview-samples/new-window-user-agent | contextMenu webview | webview-samples/shared-script | webview | webview-samples/user-agent | webview | webview-samples/webview | geolocation getUserMedia pointerLock webview | window-options | fullscreen | window-state | fullscreen | windows | framelessWindows | sample_table_autogen_end THIS TABLE IS AUTOGENERATED! PLEASE, DONT EDIT IT DIRECTLY! Samples by features feature_table_autogen_start THIS TABLE IS AUTOGENERATED! PLEASE, DONT EDIT IT DIRECTLY! API or feature | Samples --- | --- alarms | todomvc appview | appview_host-app bluetooth | bluetooth-samples_battery-service-demo bluetooth-samples_device-info-demo bluetooth-samples_heart-rate-sensor ioio clipboard | calculator diff text-editor commands | mini-code-edit contextMenu | context-menu mini-code-edit webview-samples_multi-tab-browser webview-samples_new-window-user-agent dart | dart desktopCapture | desktop-capture fileSystem | diff filesystem-access image-edit mini-code-edit text-editor todomvc usb-label-printer web-store framelessWindows | clock frameless-window gdrive io2012-presentation manga-cam mdns-browser multicast platform-title webgl-pointer-lock windows fullscreen | window-options window-state gcm | gcm-notifications geolocation | appsquare clock weather webview-samples_webview getUserMedia | appview_embedded-app camera-capture io2012-presentation io2012-presentation_servo manga-cam servo usb-label-printer webview-samples_webview hid | blink1 hid identity | appsquare gdrive github-auth identity instagram-auth one-time-payment tasks web-store in-app-payments | managed-in-app-payments mediaGallery | media-gallery messaging | messaging_app1 messaging_app2 messaging_extension multicast old_sockets | parrot-ar-drone optionalPermissions | optional-permissions usb-label-printer usb_knob pointerLock | webgl-pointer-lock webview-samples_webview print | printing richNotifications | clock gcm-notifications messaging_extension rich-notifications todomvc sandbox | sandbox sandboxed-content serial | io2012-presentation io2012-presentation_servo serial-control-signals serial_adkjs_app serial_espruino serial_ledtoggle servo sockets | mdns-browser multicast parrot-ar-drone tcpserver telnet udp webserver websocket-server storage | analytics appsquare clock diff filesystem-access gcm-notifications hello-world-sync image-edit io2012-presentation multicast one-time-payment printing restarted-demo todomvc url-handler weather web-store webview-samples_declarative-web-request webview-samples_insert-css syncFileSystem | manga-cam syncfs-editor todomvc systemInfo | mdns-browser printing systemInfo tcpserver webserver tts | tts usb | blink1 usb-label-printer usb_device-info usb_knob webstore | web-store webview | appengine-channelapi_app io2012-presentation tcpserver url-handler webview-samples_browser webview-samples_declarative-web-request webview-samples_insert-css webview-samples_local-resources webview-samples_multi-tab-browser webview-samples_new-window webview-samples_new-window-user-agent webview-samples_shared-script webview-samples_user-agent webview-samples_webview feature_table_autogen_end THIS TABLE IS AUTOGENERATED! PLEASE, DONT EDIT IT DIRECTLY! Mobile support You can generate native mobile versions of the samples below using the procedure described here. mobile_table_autogen_start THIS TABLE IS AUTOGENERATED! PLEASE, DONT EDIT IT DIRECTLY! SampleAndroid supportiOS support analyticsSupported.Supported. calculatorSupported. Visual issues caused by fixed-size layoutSupported. Visual issues caused by fixed-size layout dartSupported. Visual issues caused by fixed-size layout hello-worldSupported.Supported. hello-world-syncSupported. sync storage doesnt actually sync - works localSupported. sync storage doesnt actually sync - works local identitySupported. You need to add an Android OAuth app in the Cloud API console of the OAuth project. The apps SHA1 can be the debug one (see more here), and the package name is org.chromium.identity.MyApp. If you dont add the Android OAuth app and tries to use the OAuth client-id from the Chrome app, you will get a generic message GoogleAuthException parrot-ar-droneSupported. Communication to the Drone works, but the UI requires a connected gamepad. restarted-demoSupported. Restart must be done via Safari remote debugging. rich-notificationsSupported. tasksSupported. todomvcSupported. udpSupported. weatherSupported. webserverSupported. Directory picking doesnt work on some versions of Android websocket-serverSupported. mobile_table_autogen_end THIS TABLE IS AUTOGENERATED! PLEASE, DONT EDIT IT DIRECTLY! Libraries and tools Google APIs client library for Chrome Apps Google Analytics for Chrome Apps and Extensions