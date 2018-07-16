about slate slate is a window management application similar to divvy and sizeup except better and free originally written to replace them due to some limitations in how each work it attempts to overcome them by simply being extremely configurable as a result it may be a bit daunting to get configured but once it is done the benefit is huge slate currently works on mac os x 10 6 and above summary of features highly customizable bind keystrokes to move and or resize windows directionally focus windows activate preset layouts create delete and activate snapshots of the current state of windows set default layouts for different monitor configurations which will activate when that configuration is detected window hints an intuitive way to change window focus beta a better more customizable application switcher credits big thanks to philc for the window hints idea and initial implementation as well as plenty of other suggestions and improvement ideas using slate installing slate new installation instructions note you must turn on the accessibility api by checking system preferences universal access enable access for assistive devices direct download dmg tar gz terminal just run this in your terminal cd applications curl http www ninjamonkeysoftware com slate versions slate latest tar gz tar xz configuring slate new you may now use a slate js file to configure slate using javascript this allows for much more complex and dynamic configurations than the normal slate configuration style below you can check out the documentation for this here slate is configured using a slate file in the current users home directory configuration is loaded upon running slate you can also re load the config using the load config menu option on the status menu use this at your own risk it is better to simply restart slate note if no slate file exists in the current users home directory the default config file will be used configuration is split into the following directives config for global configurations alias to create alias variables layout to configure layouts default to default certain screen configurations to layouts bind for key bindings source to load configs from another file note is the comment character anything after a will be ignored expressions some directives allow parameters that can be expressions the following strings will be replaced with the appropriate values when using expressions screenoriginx target screens top left x coordinate should not be used in window hints configs screenoriginy target screens top left y coordinate should not be used in window hints configs screensizex target screens width screensizey target screens height windowtopleftx windows current top left x coordinate should not be used in window hints configs windowtoplefty windows current top left y coordinate should not be used in window hints configs windowsizex windows width windowsizey windows height newwindowsizex windows new width after resize only usable in topleftx and toplefty should not be used in configs newwindowsizey windows new height after resize only usable in topleftx and toplefty should not be used in configs windowhintswidth the value of the windowhintswidth config only usable in windowhintstopleftx and windowhintstoplefty windowhintsheight the value of the windowhintsheight config only usable in windowhintstopleftx and windowhintstoplefty in addition to the variables above expressions can be used with the following functions and operators e g 1 1 2 e g 1 1 0 e g 2 2 4 e g 4 2 2 e g 3 2 9 sum e g sum 1 2 3 6 count e g count 4 5 6 3 min e g min 1 3 5 1 max e g max 1 3 5 5 average e g average 1 2 3 4 2 5 median e g median 1 2 3 10 15 3 stddev e g stddev 1 2 3 4 5 1 4142135623730951 sqrt e g sqrt 9 3 0 log e g log 100 2 0 ln e g ln 8 2 0794415416798357 exp e g exp 2 7 3890560989306504 this is e parameter floor e g floor 1 9 1 0 ceiling e g ceiling 1 1 2 0 abs e g abs 1 1 trunc e g trunc 1 1123123123 1 0 random e g random 0 20607629744336009 random float between 0 and 1 randomn e g randomn 10 4 random integer between 0 and parameter 1 note when using expressions spaces are not allowed the config directive the config directive follows the following format config name value list of allowed configs example config defaulttocurrentscreen true note the slate file is read top down directives that come before config directives may not have the config applied as such it is best to put config directives at the top of your slate file the alias directive the alias directive follows the following format alias name value when you set an alias you can refer to it in any directive sequentially after that alias directive by referencing like name example alias bot right 2nd mon move screenoriginx 2 screensizex 3 screenoriginy screensizey 2 screensizex 3 screensizey 2 1 will allow you to use bot right 2nd mon as a reference to move screenoriginx 2 screensizex 3 screenoriginy screensizey 2 screensizex 3 screensizey 2 1 in any directive following the alias including other alias directives the layout directive the layout directive follows the following format layout name app name options operations where name the name you want to use to reference the layout app name single quoted name of the application to add to the layout or before or after options a comma separated list of options for this application cannot be used with before or after operations a pipe separated list of operations move resize push nudge throw or corner possible options name function ignore fail this will let slate move to the next operation if the current operation fails to resize move on the current window repeat this will repeat the list of operations if the number of windows is larger than the number of operations repeat last this will repeat the last operation in the list if the number of windows is larger than the number of operations main first this will cause the main window to always use the first operation main last this will cause the main window to always use the last operation mutally exclusive with main first sort title this will cause the window operations to be triggered on the windows in sorted order by the window title can be used with main first or main last title order order this will cause the operations to be triggered on the windows starting with order which is a semi colon separated list of window titles title order regex order this will cause the operations to be triggered on the windows starting with the order which is a semi colon separated list of window title regexes to match note that once a match is seen the next regex will be used to match this means if you have two windows that match the same regex only the first one seen will be matched the second will not you can have multiple layout directives that point to the same name in order to link any number of applications to the same layout example layout mylayout iterm push up bar resize screensizey 2 push down bar resize screensizey 2 layout mylayout google chrome push left bar resize screensizex 2 push right bar resize screensizex 2 layout mylayout before shell path opt local bin mvim before layout mylayout after shell path opt local bin mvim after will create a layout called mylayout with two operations for iterm and two operations for google chrome when activated the first window of iterm will be moved using the first operation in the first list and the second window of iterm will be moved using the second operation in the first list in addition the first window of google chrome will be moved using the first operation in the second list and the second window of google chrome will be moved using the second operation in the second list finally the operation shell path opt local bin mvim before will be run before any applications are moved and the operation shell path opt local bin mvim after will be run after any applications are moved before and after may also be used if the layout doesnt have any applications tied to it also you may specify multiple before or after lines they will be run in the order that they appear more information on how to actually use these layouts can be found under the layout operation in the bind directive section the default directive the default directive follows the following format tokens may be separated by any number of spaces default layout or snapshot name screen configuration where layout or snapshot name the name of the layout or snapshot you want to default to screen configuration either count number of screens or resolutions semicolon separated list of resolutions this directive will cause any screen configuration change add monitor remove monitor screen resolution change to trigger a search for a default layout or snapshot if the screen configuration matches one of the defaults set the layout or snapshot matching layout or snapshot name will be triggered for example default mylayout count 2 will trigger mylayout anytime the screen configuration changes to have 2 monitors also default mylayout2 resolutions 1440x900 1024x768 1680x1050 will trigger mylayout2 anytime the screen configuration changes to have exactly 3 monitors with resolutions 1440x900 1024x768 and 1680x1050 the bind directive the bind directive follows one of the following formats tokens may be separated by any number of spaces bind key modifiers operation parameter bind key modal key operation parameter key key is a reference to a key on the keyboard see allowed keys for a complete list for example the s key would simply be s while the 1 key on the number pad would be pad1 modifiers modifiers is a comma or semicolon separated list of standard modifier keys allowed modifiers are control ctrl option alt alt command cmd shift shift note if you bind any binding to cmd tab or cmd shift tab slate will completely disable the default mac os x application switcher note bindings that are used by mac os x spaces expose and mission control will override slate bindings be sure to turn these bindings off if you want to use them in slate modal key modal key is any one of the allowed keys if using a modal key pressing that key will cause the slate menu bar icon to change indicating modal mode is activated then clicking key will activate the binding modal mode will remain active until key has been pressed or modal key is pressed again you may specify multiple bindings with the same modal key as long as key is different also modal key can accompany a comma or semicolon separated list of modifier keys listed above this will cause that entire keystroke to be considered the modal activation binding for example bind 1 f4 ctrl alt will result in the modal keystroke being ctrl alt f4 after pressing that keystroke modal mode will be activated and pressing 1 after that will activate the binding modal toggle behavior if you add toggle to the end of a modal binding it will cause that binding to not end the modal mode for example with the binding 1 ctrl f4 you press ctrl f4 and then press 1 to activate the binding once that binding is activated modal mode will end and you have to press ctrl f4 again to activate it however with the binding 1 ctrl f4 toggle pressing ctrl f4 will toggle modal mode pressing 1 will activate the binding but not end modal mode to end modal mode press ctrl f4 again or use the config modalescapekey operation operations define what to actually do to the focused window screens some operations allow you to specify a screen here are the list of possible values for screen integer representing the screen id indexed at 0 screens are ordered from left to right by x coordinate of the origin which is the top left point if orderscreenslefttoright is set to false the screen id is the mac os internal id indexed at 0 if orderscreenslefttoright is set to false but you still want to reference screens in the default ordered mode prefix the screen id with ordered screen resolution in the format widthxheight e g 1440x900 screen direction relative to the current screen left right up above down below next or previous represents the currentid 1 or currentid 1 screen allowed operations are move move resize the window any which way move topleftx toplefty sizex sizey screen topleftx top left x coordinate of the windows desired position can be an expression toplefty top left y coordinate of the windows desired position can be an expression sizex width of the windows desired position can be an expression sizey height of the windows desired position can be an expression screen optional the reference to the screen of the windows desired position if this is not specified it will default to the screen the window is currently on see the table at the beginning of the operation section for more information example bind pad1 ctrl move 0 0 100 100 1 will bind the keystroke ctrl numpad1 to moving the window to the screen at index 1 with top left coordinate 0 0 and size 100 100 note remember to offset with screenoriginx in your topleftx and screenoriginy in your toplefty when using the screen option or when using multiple screens in general or your move operation will offset from the default origin 0 0 which is the origin of screen 0 resize resize the window keeping top left the same resize x y anchor x amount to resize width either as a percent or a hard value 10 or 100 y amount to resize height either as a percent or a hard value 10 or 100 anchor optional which corner to anchor on top left top right bottom left bottom right default is top left example bind right ctrl resize 10 0 will bind the keystroke ctrl rightarrow to increase the width the current window by 10 note ctrl rightarrow is used by default in mac os x by spaces be sure to turn these bindings off if you want to use them in slate push push the window to the edge of the screen push direction style direction top up bottom down left right style optional none center bar bar resize expression default is none screen optional the reference to the screen of the windows desired position if this is not specified it will default to the screen the window is currently on see the table at the beginning of the operation section for more information example bind up alt ctrl push up will bind the keystroke alt ctrl uparrow to push the window so that it is aligned with the top of the screen nudge nudge the window in any direction nudge x y x amount to nudge x either as a percent or a hard value 10 or 100 y amount to nudge y either as a percent or a hard value 10 or 100 example bind left ctrl shift nudge 100 0 will bind the keystroke ctrl shift leftarrow to nudge the window 100 pixels to the left throw throw the window to any screens origin throw screen style screen the screen you want to throw the window to 0 indexed style optional resize resize x expression y expression default will not resize example bind pad1 alt ctrl throw 1 resize will bind the keystroke alt ctrl numpad1 to throw the window to the 2nd screen and resize it to fit that screen corner move resize the window into a corner corner direction style direction top left top right bottom left bottom right style optional resize x expression y expression default will not resize screen optional the reference to the screen of the windows desired position if this is not specified it will default to the screen the window is currently on see the table at the beginning of the operation section for more information example bind 1 ctrl corner top left resize screensizex 2 screensizey 2 will bind the keystroke ctrl 1 to move the window to the top left corner and resize it to 1 4 of the screen shell execute a shell command shell options command command required the command to run note that it is a quoted string options optional a space separated list of wait block slate until the shell command exits useful when using shell commands in a sequence binding path the inital working directory to use when starting the command for example path code would set the inital working directory to code example bind 1 ctrl wait path code opt local bin mvim will bind the keystroke ctrl 1 to run the command opt local bin mvim with the current working directory of code slate will also block until the command is done note that you may not use the tilda home directory shortcut within the command itself it is only allowed within the path hide hide one or more applications hide applications applications a comma separated list of application names individual application names must be surrounded by quotes you can also specify current all or all but for the application name no quotes current will apply to the currently focused application all will apply to all open applications and all but app name will apply to all open applications except app name note that when trying to hide all it will not work as intended because os x will not allow every visible app to be hidden hiding all will hide all apps but os x will auto show one of the apps that were hidden example bind 1 ctrl hide iterm google chrome will bind the keystroke ctrl 1 to hide iterm and google chrome show show one or more applications show applications applications a comma separated list of application names individual application names must be surrounded by quotes you can also specify current all or all but for the application name no quotes current will apply to the currently focused application all will apply to all open applications and all but app name will apply to all open applications except app name example bind 1 ctrl show iterm google chrome will bind the keystroke ctrl 1 to show unhide iterm and google chrome toggle toggle one or more applications toggle applications applications a comma separated list of application names individual application names must be surrounded by quotes you can also specify current all or all but for the application name no quotes current will apply to the currently focused application all will apply to all open applications and all but app name will apply to all open applications except app name note that when trying to toggle all it will may not work as intended because os x will not allow every visible app to be hidden if at any point during the toggling all apps become hidden os x will auto show one of the apps that were hidden example bind 1 ctrl toggle iterm google chrome will bind the keystroke ctrl 1 to toggle iterm and google chrome toggle meaning if the individual application is currently hidden it will be shown and if it is currently shown it will be hidden note if you specify current in this toggle operation it will not toggle properly because after the current application is hidden it is no longer the current application anymore chain chain multiple operations to one binding chain opandparams1 opandparams2 opandparamsx any operation string except sequence hint and grid example bind 1 ctrl chain push up push right push down push left will bind the keystroke ctrl 1 to push up on the first press then push right on the second press then push down on the third press the push left on the fourth press and rotate back to pushing up on the fifth press etc sequence activate a sequence of operations in one binding sequence opandparams1 separator opandparams 2 opandparamsx any of the above operation strings except chain and grid hint must be last if present separator or will cause the next operation to be performed on the window focused at the time of execution of that operation will cause the next operation to be performed on the window focused at the start of the chain example bind 1 ctrl sequence focus right push left push right will bind the keystroke ctrl 1 to first focus the window to the right then push the previously focused window to the left then push the newly focused window to the right obviously hint will ignore and and just display because it doesnt care which window was focused layout activate a layout layout name name the name of the layout to activate set using the layout directive example bind 1 ctrl layout mylayout will bind the keystroke ctrl l to activate the layout called mylayout note that the layout must be created before you bind it focus focus a window in a direction or from an application focus direction app direction right left up above down below behind app an app name surrounded by quotes example bind 1 ctrl focus above will bind the keystroke ctrl 1 to focus the window slate finds to be above the currently focused window from any application minimized and hidden windows are ignored a couple global configuration options set using the config directive exist to tweak this also up and above are the same down and below are also the same bind 1 ctrl focus iterm will bind the keystroke ctrl 1 to focus the main window of the application iterm the main window is the last focused window of that application snapshot create a snapshot of your current window locations snapshot name options name the name of the snapshot to create used in delete snapshot and activate snapshot options optional a semicolon separated list of any of the following options save to disk saves the snapshot to disk so slate will load it when it starts up next stack treats this snapshot as stack so you can use this binding multiple times to push snapshots on the stack example bind 1 ctrl snapshot thename save to disk stack will bind the keystroke ctrl 1 to create a snapshot called thename save that snapshot to disk and treat it as a stack so you can hit the keystroke multiple times to push snapshots onto the stack note there is a menu option to take a snapshot of the current screen configuration delete snapshot delete a snapshot delete snapshot name options name the name of the snapshot to delete options optional a semicolon separated list of any of the following options all if the snapshot is a stack if it isnt this option is useless this will delete all snapshots in the stack if this option is not specified the default is to only delete the top snapshot of the stack example bind 1 ctrl delete snapshot thename all will bind the keystroke ctrl 1 to delete the snapshot called thename if it exists this will delete all instances of thename meaning if you have pushed multiple snapshots on the stack it will completely clear them all activate snapshot activate a snapshot activate snapshot name options name the name of the snapshot to activate options optional a semicolon separated list of any of the following options delete this will delete the snapshot after activating it if the snapshot is a stack it will pop the top snapshot off and keep the rest example bind 1 ctrl activate snapshot thename delete will bind the keystroke ctrl 1 to activate the snapshot called thename if it exists this will also delete the snapshot or pop it off the stack if the snapshot is a stack note there is a menu option to activate the snapshot that you may have created using the menu option hint show window hints similar to link hints in vimium except for windows hint characters characters optional a simple string of characters to be used for the hints each hint consists of one character if there are more windows than characters then some windows will not get hints this string can contain any of the single character allowed keys letters may be upper case or lower case but both will be bound to the lowercase letter for the hint using upper or lower case only changes how they are displayed the default string of characters is abcdefghijklmnopqrstuvwxyz0123456789 example bind 1 ctrl hint qwertyuiop will bind the keystroke ctrl 1 to show window hints using the letters q w e r t y u i o and p this will show an overlay in the top left corner of every window on screen containing one of those letters while the overlays are showing if one of those letters is pressed the corresponding window will be focused if there are more than 10 windows some windows will not get hints pressing esc will dismiss the hints note there are tons of config options to tweak this grid show a grid to one off resize and move windows grid options options is a whitespace separated list of padding integer the padding between cells screenref width height width and height are integers specifying the width and height of the grid number of cells not absolute size screenref is either the screenid or screen resolution widthxheight example bind 1 ctrl grid padding 5 1680x1050 16 9 1050x1680 9 16 will bind the keystroke ctrl 1 to show grids on each screen the default width and height are 12 this will set the padding between the cells to be 5 also this will change the width and height of the grid on the monitor with the resolution 1680x1050 to 16 and 9 respectively for the monitor with the resolution 1050x1680 it will set the width to 9 and height to 16 if you have multiple monitors the grid that is on the same screen as your mouse pointer will be focused if you want to use a grid on a different monitor you must click it first and then click drag note there are a bunch of config options to tweak how this looks relaunch relaunch slate relaunch example bind 1 ctrl relaunch will bind the keystroke ctrl 1 to relaunch slate this will also reload the slate file from scratch undo undo an operation undo example bind 1 ctrl undo will bind the keystroke ctrl 1 to undo the last binding that was triggered by default you can undo up to the last 10 commands this can be changed using the undomaxstacksize config also you can only undo movement based operations focus related operations will not undo switch beta a better application switcher switch if you bind any binding to cmd tab or cmd shift tab slate will completely disable the default mac os x application switcher example bind tab cmd switch will disable the default mac os x application switcher and bind the keystroke cmd tab to a better application switcher note there are tons of config options to tweak this the source directive the source directive follows the following format tokens may be separated by any number of spaces source filename optional if exists where filename is the name of a file containing any of the directives above including source if no absolute path is specified the users home directory will be prepended to filename if the user specifies the option if exists as the second argument slate will not complain if it cannot find the file for example source slate test if exists will append all of the configurations from the file slate test to the current configuration if the file slate test exists note you may use any aliases layouts etc that you specify before the source directive in the file you source any aliases layouts etc specified after cannot be used additionally any aliases layouts etc that you specify in the file you source can be used after the source directive example config you can check out my own config here useful stuff kvs has created a sublime text 2 preference for slate files here trishume has done a really nice writeup on getting started with slate here contact please send all questions bug reports suggestions or general commentary to jigish patel or create an issue on github allowed keys note if you bind any binding to cmd tab or cmd shift tab slate will completely disable the default mac os x application switcher 0 1 2 3 4 5 6 7 8 9 a b backslash c caps d delete down e end esc f f1 f10 f11 f12 f13 f14 f15 f16 f17 f18 f19 f2 f20 f3 f4 f5 f6 f7 f8 f9 g h help home i j k l left m mute n o p pad pad pad pad pad pad0 pad1 pad2 pad3 pad4 pad5 pad6 pad7 pad8 pad9 pad padclear padenter pagedown pageup q r return right s space t tab u up v w x y z