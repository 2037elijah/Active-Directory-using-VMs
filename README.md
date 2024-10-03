# Active-Directory-using-VMs
# Hello!, this repository consists of the steps I took to create an Active Directory (AD) using VirtualBox. 
# I created this AD to get a better understanding of the infrastructure and Windows networking. Inspired by Josh Madakor"s Youtube tutorials.
# I also wanted to detail some potential pitfalls that may arise during setup. This project is a good starting point for anyone new to IT.
#------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Goals: The goal of this project is to provide insight into what an AD is, demonstrate its setup, and give you a test enviroment that can be used for future projects.
#-----------------------------------------------------------------------------------------------------------------------------------------------------------------
# Technologies Used: This is what you will need to begin: 
# VirtualBox 7.0 ( Oracle.com )
# Windows 10 ISO ( Microsoft.com )
# Windows Server 2019 ISO ( Microsoft.com )
#------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Setup Steps:
# Once you have these downloaded and installed the first thing we will do is setup the first virtual machine which will be the Domain Controller that will house AD.
# next we will give this VM two network adapters, one will connect to the outside internet and the other will connect to the virtual box sort of private network ----  
# that the clients will connect to. 
#-----------------------------------------------------
# after the vitual machine is ceated you will install Windows server 2019 and then assign ip addressing for the internal network ---- 
# the external network will automatically get ip addressing from your home network ---- 
# or like your home router so we don't have to worry about it. 
# after we have ip addressing setup we're going to name the server and then we're going to install active directory and create our domain ---- 
# then we're going to configure that and routing so the clients on the private network can reach the internet through the domain controller.
#-----------------------------------------------------
# next we're going to set up a dhcp on the domain controller so when we create our windows 10 machine ----
# it can automatically get an ip address and then the last thing we do on the domain controller before we create our client virtual machine is ---- 
# we're going to run a powershell script that will automatically create a thousand users in AD.
#-----------------------------------------------------
# after creating the users we're going to create another virtual machine and install windows 10 on it ---- 
# and that virtual machine will be connected to the private virtual box network ----
# we're going to name that machine client1 and join it to the domain and then we're going to log into it with one of our domain accounts.
# After this the project can be considered done. 
#-------------------------------------------------------
# NOTE: Be sure that you have a computer with enough memory, storage and processing power.
# Allocate sufficient resources (CPU and RAM) to each VM during setup. 
# Insufficient resources may lead to issues, especially when running multipe VMs. 
#---------------------------------------------------------------------------------------------------------------------------------------------------------------
# SETBACKS: Here are some the challenges I faced: 
# I had not enough memory and processing power to run Client1 so the project for me stopped at running the 1K users from Powershell.
# You will need a Guest Additions CD image, if you are on Windows as your base OS you can find it in the Devices tab of the Server 2019 VM.
# Once you have the guest additions ISO/CD Image inserted, you will find it on "This PC" of the first VM running Server 2019.
# I recommended that when you create your 2nd VM with Windows 10, to use one core and atleast 3-4Gb if you do not have a lot of memory and proccessing power ---->
# this will be a bit slow but will get you further along in creating Client1.

# By following these steps, you can successfully setup an AD enviroment using VMs. THis enviroment can serve as a valuable  testbed for further projects.
