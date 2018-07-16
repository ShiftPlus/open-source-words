minio quickstart guide minio is an object storage server released under apache license v2 0 it is compatible with amazon s3 cloud storage service it is best suited for storing unstructured data such as photos videos log files backups and container vm images size of an object can range from a few kbs to a maximum of 5tb minio server is light enough to be bundled with the application stack similar to nodejs redis and mysql docker container stable docker pull minio minio docker run p 9000 9000 minio minio server data edge docker pull minio minio edge docker run p 9000 9000 minio minio edge server data please visit minio docker quickstart guide for more here macos homebrew install minio packages using homebrew sh brew install minio stable minio minio server data note if you previously installed minio using brew install minio then it is recommended that you reinstall minio from minio stable minio official repo instead sh brew uninstall minio brew install minio stable minio binary download platform architecture url apple macos 64 bit intel https dl minio io server minio release darwin amd64 minio sh chmod 755 minio minio server data gnu linux binary download platform architecture url gnu linux 64 bit intel https dl minio io server minio release linux amd64 minio sh wget https dl minio io server minio release linux amd64 minio chmod x minio minio server data microsoft windows binary download platform architecture url microsoft windows 64 bit https dl minio io server minio release windows amd64 minio exe sh minio exe server d \photos freebsd port install minio packages using pkg sh pkg install minio sysrc minio enable yes sysrc minio disks home user photos service minio start install from source source installation is only intended for developers and advanced users if you do not have a working golang environment please follow how to install golang sh go get u github com minio minio allow port access for firewalls by default minio uses the port 9000 to listen for incoming connections if your platform blocks the port by default you may need to enable access to the port iptables for hosts with iptables enabled rhel centos etc you can use iptables command to enable all traffic coming to specific ports use below command to allow access to port 9000 sh iptables a input p tcp dport 9000 j accept service iptables restart below command enables all incoming traffic to ports ranging from 9000 to 9010 sh iptables a input p tcp dport 9000 9010 j accept service iptables restart ufw for hosts with ufw enabled debian based distros you can use ufw command to allow traffic to specific ports use below command to allow access to port 9000 sh ufw allow 9000 below command enables all incoming traffic to ports ranging from 9000 to 9010 sh ufw allow 9000 9010 tcp firewall cmd for hosts with firewall cmd enabled centos you can use firewall cmd command to allow traffic to specific ports use below commands to allow access to port 9000 sh firewall cmd get active zones this command gets the active zone s now apply port rules to the relevant zones returned above for example if the zone is public use sh firewall cmd zone public add port 9000 tcp permanent note that permanent makes sure the rules are persistent across firewall start restart or reload finally reload the firewall for changes to take effect sh firewall cmd reload test using minio browser minio server comes with an embedded web based object browser point your web browser to http 127 0 0 1 9000 ensure your server has started successfully test using minio client mc mc provides a modern alternative to unix commands like ls cat cp mirror diff etc it supports filesystems and amazon s3 compatible cloud storage services follow the minio client quickstart guide for further instructions pre existing data when deployed on a single drive minio server lets clients access any pre existing data in the data directory for example if minio is started with the command minio server mnt data any pre existing data in the mnt data directory would be accessible to the clients the above statement is also valid for all gateway backends explore further minio erasure code quickstart guide use mc with minio server use aws cli with minio server use s3cmd with minio server use minio go sdk with minio server the minio documentation website contribute to minio project please follow minio contributors guide license