bytecode viewer bytecode viewer is an advanced lightweight java bytecode viewer gui java decompiler gui bytecode editor gui smali gui baksmali gui apk editor gui dex editor gui apk decompiler gui dex decompiler gui procyon java decompiler gui krakatau gui cfr java decompiler gui fernflower java decompiler gui dex2jar gui jar2dex gui jar jar hex viewer code searcher debugger and more its written completely in java and its open sourced its currently being maintained and developed by konloch there is also a plugin system that will allow you to interact with the loaded classfiles for example you can write a string deobfuscator a malicious code searcher or something else you can think of you can either use one of the pre written plugins or write your own it supports groovy scripting once a plugin is activated it will execute the plugin with a classnode arraylist of every single class loaded in bcv this allows the user to handle it completely using asm code from various projects has been used including but not limited to j ret by waterwolf jhexpane by sam koivu rsynaxpane by robert futrell commons io by apache asm by ow2 fernflower by stiver procyon by mstrobel cfr by lee benfield cfide by bibl smali by jesusfreke dex2jar by pxb1 krakatau by storyyeller jd gui jd core by the java decompiler team enjarify by storyyeller contributors konloch bibl fluke righteous sahitya pavurala priav03 afffsdd szperak zooty samczsun itzsomebody if i missed you please feel free to contact me konloch or konloch gmail com website https bytecodeviewer com source code https github com konloch bytecode viewer bin archive https github com konloch bytecode viewer releases java docs https the bytecode club docs bytecode viewer license copyleft https raw githubusercontent com konloch bytecode viewer master license report bugs or below https github com konloch bytecode viewer issues discussion forum https the bytecode club forumdisplay php fid 69 key features krakatau integration for bytecode assembly disassembly smali baksmali integration you can now edit class files dex files via smali apk dex support using dex2jar and jar2dex its able to load and save apks with ease java decompiler it utilizes fernflower procyon and cfr for decompilation bytecode decompiler a modified version of cfides hex viewer powered by jhexpane each decompiler editor viewer is toggleable you can also select what will display on each pane fully featured search system search through strings functions variables and more a plugin system with built in plugins show all strings malicious code scanner string decrypters etc fully featured scripting system that supports groovy ez inject graphically insert hooks and debugging code invoke main and start the program recent files recent plugins and more give it a try for yourself command line input help displays the help menu list displays the available decompilers decompiler decompiler selects the decompiler procyon by default i input file selects the input file jar class apk zip dex all work automatically o output file selects the output file java or java bytecode t target classname must either be the fully qualified classname or all to decompile all as zip nowait doesnt wait for the user to read the cli messages are you a java reverse engineer do you want to learn join the bytecode club today https the bytecode club