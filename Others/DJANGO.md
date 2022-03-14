Django Cheatsheet
===================

- - - - 
## What Is Django? ##

Django is an open source web framework for Python
- It has a pre-defined set of code to perform common actions

&nbsp;

#### What Is Django REST Framework? ####
It is another framework that provides a set of features for making standard REST APIs

- - - - 

### Steps on creating new Virtual Machine and Virtual Environment ###

1. Initialize a vagrant file inside the project folder using the terminal:
 ```console
 ~% vagrant init ubuntu/bionic64
 ```

2. Inside the new vagrant file, replace all the code with this new lines:
```ruby

# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
 # The most common configuration options are documented and commented below.
 # For a complete reference, please see the online documentation at
 # https://docs.vagrantup.com.

 # Every Vagrant development environment requires a box. You can search for
 # boxes at https://vagrantcloud.com/search.
 config.vm.box = "ubuntu/bionic64"
 config.vm.box_version = "~> 20200304.0.0"

 config.vm.network "forwarded_port", guest: 8000, host: 8000

 config.vm.provision "shell", inline: <<-SHELL
   systemctl disable apt-daily.service
   systemctl disable apt-daily.timer
 
   sudo apt-get update
   sudo apt-get install -y python3-venv zip
   touch /home/vagrant/.bash_aliases
   if ! grep -q PYTHON_ALIAS_ADDED /home/vagrant/.bash_aliases; then
     echo "# PYTHON_ALIAS_ADDED" >> /home/vagrant/.bash_aliases
     echo "alias python='python3'" >> /home/vagrant/.bash_aliases
   fi
 SHELL
end
```
3. Run the Server.
  - To run the server, you first need to run this command inside the project folder with the terminal:
```console
 ~% vagrant up
 ```
4. Once the server is running, to connect to it: 
```console
 ~% vagrant ssh
 ```
 When you do this, you will be able to run commands inside the vm with that terminal.
 To exit, just type exit.
 ```console
 ~% exit
 ```

 All the files create and modified inside the VM, will also be changed in the project folder, this is because the files are Synchronous.

&nbsp;

 5. Initialize Python: 
```console
 ~% python -m venv ~/env
 ```
 This is creating the environment in the home directory of our Vagrant server. This will prevent the sincronization of the files.

&nbsp;

 6. Activate Virtual Environment on our Virtual Machine: 
```console
 ~% source ~/env/bin/activate
 ```

  To deactivate it, just type deactivate.
 ```console
 ~% deactivate
 ```

&nbsp;
  7. Install django and djangorestframework in the VE: 
```console
 ~% pip install ...
 ```
- - -


### Creating new django Project ###
1. Initialize the project:
   
```console
 ~% django-admin.py startproject profiles_project .
 ```
This is calling the django script passing the startproject argument, and passing the name of the new project called profiles_project

&nbsp;

2. Create App inside the project:
```console
 ~% python manage.py startapp profiles_api

 ```
This is creating a new Django app inside our project called profiles_api

- - -

### Django models ###

- We use models in Django to describe the data we need for our application. Then, Django uses these models to set up and configure our databases to store our data effectively.

- Each model maps a specific table within our Database. 
- Django handles the relationship between our models and the database for us, so we never need to write an sql statements or interact with the database directly. 
- - -