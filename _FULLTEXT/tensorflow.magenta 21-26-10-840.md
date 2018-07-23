magenta is a research project exploring the role of machine learning in the process of creating art and music primarily this involves developing new deep learning and reinforcement learning algorithms for generating songs images drawings and other materials but its also an exploration in building smart tools and interfaces that allow artists and musicians to extend not replace their processes using these models magenta was started by some researchers and engineers from the google brain team but many others have contributed significantly to the project we use tensorflow and release our models and tools in open source on this github if youd like to learn more about magenta check out our blog where we post technical details you can also join our discussion group this is the home for our python tensorflow library to use our models in the browser with tensorflow js head to the magenta js repository getting started installation using magenta playing a midi instrument development environment advanced installation python pip magenta maintains a pip package for easy installation we recommend using anaconda to install it but it can work in any standard python environment we support both python 2 2 7 and python 3 3 5 these instructions will assume you are using anaconda note that if you want to enable gpu support you should follow the gpu installation instructions below automated install if you are running mac os x or ubuntu you can try using our automated installation script just paste the following command into your terminal curl https raw githubusercontent com tensorflow magenta master magenta tools magenta install sh tmp magenta install sh bash tmp magenta install sh after the script completes open a new terminal window so the environment variable changes take effect the magenta libraries are now available for use within python programs and jupyter notebooks and the magenta scripts are installed in your path note that you will need to run source activate magenta to use magenta every time you open a new terminal window manual install if the automated script fails for any reason or youd prefer to install by hand do the following steps first download the python 2 7 miniconda installer you can skip this step if you already have any variant of conda installed next create and activate a magenta conda environment using python 2 7 with jupyter notebook support conda create n magenta python 2 7 jupyter source activate magenta install the magenta pip package pip install magenta note in order to install the rtmidi package that we depend on you may need to install headers for some sound libraries on linux this command should install the necessary packages sudo apt get install build essential libasound2 dev libjack dev the magenta libraries are now available for use within python programs and jupyter notebooks and the magenta scripts are installed in your path note you will need to run source activate magenta to use magenta every time you open a new terminal window gpu installation if you have a gpu installed and you want magenta to use it you will need to follow the manual install instructions but with a few modifications first make sure your system meets the requirements to run tensorflow with gpu support next follow the manual install instructions but install the magenta gpu package instead of the magenta package pip install magenta gpu the only difference between the two packages is that magenta gpu depends on tensorflow gpu instead of tensorflow magenta should now have access to your gpu docker another way to try out magenta is to use our docker container first install docker next run this command docker run it p 6006 6006 v tmp magenta magenta data tensorflow magenta this will start a shell in a directory with all magenta components compiled installed and ready to run it will also map port 6006 of the host machine to the container so you can view tensorboard servers that run within the container this also maps the directory tmp magenta on the host machine to magenta data within the docker session windows users can change tmp magenta to a path such as c magenta and mac and linux users can use a path relative to their home folder such as magenta warning only data saved in magenta data will persist across docker sessions the docker image also includes several pre trained models in magenta models for example to generate some midi files using the lookback melody rnn run this command melody rnn generate \ config lookback rnn \ bundle file magenta models lookback rnn mag \ output dir magenta data lookback rnn generated \ num outputs 10 \ num steps 128 \ primer melody 60 note verify that the output dir path matches the path you mapped as your shared folder when running the docker run command this example command presupposes that you are using magenta data as your shared folder from the example docker run command above one downside to the docker container is that it is isolated from the host if you want to listen to a generated midi file youll need to copy it to the host machine similarly because our midi instrument interface requires access to the host midi port it will not work within the docker container youll need to use the full development environment you may find at some point after installation that we have released a new version of magenta and your docker image is out of date to update the image to the latest version run docker pull tensorflow magenta note our docker image is also available at gcr io tensorflow magenta using magenta you can now train our various models and use them to generate music audio and images you can find instructions for each of the models by exploring the models directory to get started create your own melodies with tensorflow using one of the various configurations of our melody rnn model a recurrent neural network for predicting melodies playing a midi instrument after youve trained one of the models above you can use our midi interface to play with it interactively we also have created several demos that provide a ui for this interface making it easier to use e g the browser based ai jam development environment if you want to develop on magenta youll need to set up the full development environment the installation has three components you are going to need bazel to build packages tensorflow to run models and an up to date version of this repository first clone this repository git clone https github com tensorflow magenta git next install bazel we require the latest version currently 0 13 1 you will also need to install some required python dependencies we recommend using a conda environment and installing with pip see setup py for the current list of required dependencies finally install tensorflow to see what version of tensorflow the code currently requires check the dependency listed in setup py also verify that your environment uses a supported python version 2 7 for python 2 or 3 5 for python 3 after thats done change directory to magenta or your clone path cd magenta and then run the tests with this command bazel test magenta to build and install the pip package from source follow the pip build instructions you can also use our build script if you want to build and run commands with bazel youll need to run the package that the build step generates there are two ways to do this the first option is to look at the output of the build command to find the path to the generated file for example if you want to build the melody rnn generate script bazel build magenta models melody rnn melody rnn generate info found 1 target target magenta models melody rnn melody rnn generate up to date bazel bin magenta models melody rnn melody rnn generate bazel bin magenta models melody rnn melody rnn generate config the other option is to use the bazel run command which combines the two steps above note that if you use bazel run youll need to add an extra before the command line arguments to differentiate between bazel arguments and arguments to the command bazel run magenta models melody rnn melody rnn generate config