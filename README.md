# Vagrant_boxes
Vagrant boxes ready for import
centos7 box minimall for Virtualbox 5.1.8 

a)import the centos7.ova to your virtualbox 

b)mkdir ~/centos7; cd ~/centos7 

c)vagrant package --base "centos7"; vagrant box add centos7 package.box 

d)your centos base image is ready 

e)make your own test ex: mkdir ~/test; cd ~/test ; vagrant init centos7; vagrant up 

f)now is just vagrant ssh 
