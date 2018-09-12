## What is AWS?
* AWS is an acronym for Amazon Web Services.
* In short, it's just server cloud services.
* See here: https://aws.amazon.com/what-is-aws/

## 1) Making an AWS EC2 Instance
* See this link: https://aws.amazon.com/getting-started/tutorials/launch-a-virtual-machine/
  * Notice; Select an Ubuntu 16.04 instead of an Amazon Linux AMI in step 2 (configure step).
  * Use ssh command `ssh -i 'c:\Users\yourusername\.ssh\MyKeyPair.pem' ubuntu@{IP_Address}` instead of `ec2-user` for connecting.
  * Other options are same

## 2) Setting up the NiLearn package
* In this case, Python3.5 would already be installed. You can check it by typing `python3` in the connected AWS.
* Type `sudo apt-get update` to obtain information for packages to use.
* Type `sudo apt-get upgrade` to upgrade all installed packages to the new version.
* Type `sudo apt install python3-pip` to install Python3 package installer.
* Type `pip3 install nilearn scipy sklearn` for installing NiLearn and other packages needed for using NiLearn.
  * See https://nilearn.github.io/introduction.html#installing-nilearn
* Let's check if NiLearn is working well or not.
  * Type `python3` again. You can see the Python3 interpreter.
  * Use the command `import nilearn` and press enter. If there are any problems, the python interpreter shows some error messages.
