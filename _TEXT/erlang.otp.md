erlang otp erlang is a programming language and runtime system for building massively scalable soft real time systems with requirements on high availability otp is a set of erlang libraries which consists of the erlang runtime system a number of ready to use components mainly written in erlang and a set of design principles for erlang programs learn more about erlang and otp learn how to program in erlang examples there are several examples on the website to help you get started the below example defines a function world 0 that prints hello world in the erlang shell erlang module hello export world 0 world io format hello world\n save the file as hello erl and run erl to enter the erlang shell to compile the module erlang otp 19 erts 8 2 source 64 bit smp 4 4 async threads 10 hipe kernel poll false dtrace eshell v8 2 abort with g 1 c hello ok hello 2 hello world hello world ok learn more about the erlang syntax of modules functions and expressions on erlang org installation binary distributions erlang otp is available as pre built binary packages by most os package managers apt get install erlang compiling from source to compile erlang from source run the following commands the complete building and installation instructions can be found here git clone https github com erlang otp git cd otp otp build autoconf configure make make install alternatively you can use kerl a script that lets you easily build erlang with a few commands bug reports please visit bugs erlang org for reporting bugs the instructions for submitting bugs reports can be found here security disclosure we take security bugs in erlang otp seriously please disclose the issues regarding security by sending an email to erlang security at erlang dot org and not by creating a public issue contributing we are grateful to the community for contributing bug fixes and improvements read below to learn how you can take part in improving erlang otp we appreciate your help contribution guide read our contribution guide to learn about our development process how to propose fixes and improvements and how to test your changes to erlang otp before submitting a pull request help wanted we have a list of help wanted bugs that we would appreciate external help from the community this is a great place to get involved license erlang otp is released under the apache license 2 0 copyrightbegin copyright ericsson ab 2010 2017 all rights reserved licensed under the apache license version 2 0 the license you may not use this file except in compliance with the license you may obtain a copy of the license at http www apache org licenses license 2 0 unless required by applicable law or agreed to in writing software distributed under the license is distributed on an as is basis without warranties or conditions of any kind either express or implied see the license for the specific language governing permissions and limitations under the license copyrightend awesome erlang you can find more projects tools and articles related to erlang otp on the awesome erlang list add your project there