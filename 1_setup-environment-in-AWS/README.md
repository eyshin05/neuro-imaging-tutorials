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
  * If python3 isn't installed, use this command: `sudo apt-get install python3`.
  * For closing python, type `exit()` or press Ctrl+D.
* Type `sudo apt-get update` to obtain information for packages to use.
* Type `sudo apt-get upgrade` to upgrade all installed packages to the new version.
* Type `sudo apt install python3-pip` to install Python3 package installer.
* Type `pip3 install nilearn scipy sklearn` for installing NiLearn and other packages needed for using NiLearn.
  * See https://nilearn.github.io/introduction.html#installing-nilearn
* Let's check if NiLearn is working well or not.
  * Type `python3` again. You could see the Python3 interpreter.
  * Use the command `import nilearn` and press enter. If there are any problems, the python interpreter shows some error messages.

## 3) Installing Jupyter Notebook
* Jupyter notebook is one of Python IDEs.
   * IDE is Integrated Development Environment, like Visual Studio, X Code, R studio or MATLAB client.
   * There are many other Python IDEs like; iPython, PyCharm, Spyder, and others.
   * You can use simple text editors instead, like; Atom, Notepad++, Coda, Sublime text, or others. 
   * But, I think Jupyter notebook is suitable for researching because it is good at visualizing graphs, sharing codes, reporting results, performing trials and debugging errors (in my opinion.)
* Type `pip3 install jupyter notebook` to install the Jupyter Notebook.
  * If you want to check a notebook is installed correctly, you can type `jupyter notebook` and see many logs.
  * But in this case(AWS), you can't see a graphical IDE in your web browser. It is a same when you are setting this in a server machine without GUI. You might only show a web browser IDE when you are setting this up in your local computer with GUI.
* Check current working directory is your home folder.
  * Or just type `cd ~`.
* Type `jupyter notebook --generate-config` for making configure file of your notebook server. 
* For making a password to access, Open `python3` and Type these codes.
 ```python
 >>> from notebook.auth import passwd
 >>> passwd()
 ```
  * Type your password and save output text like `sha1:f24bafe49bb5:fffdd2ad737...`.
  * Type `exit()` to close the Python3 interpreter.
* Type `vi .jupyter/jupyter_notebook_config.py` to edit a config file.
  * Type `:a` for insert text to the file.
  * Type `G` to see the bottom of the file.
  * Insert these codes at the bottom of the file.
    ```python
    c = get_config()
    c.NotebookApp.password = u'[sha1:f24bafe49bb5:fffdd2ad737...]'
    c.NotebookApp.ip = '[Your Private AWS IP Address]'
    c.NotebookApp.port_retries = 8888
    ```
    * You can see your private IP address in the AWS EC2 Management Console page. Select the instance and see the description tab. It seems like a `123.45.67.234`.
    * If you don't want to use the port 8888 then use another number between 1024 ~ 49151.
      * https://en.wikipedia.org/wiki/Port_(computer_networking)#Common_port_numbers
  * Type `:wq!` to save this config file and quit vi editor.
  * Finally, you can run jupyter notebook server with command `jupyter notebook --no-browser`.
  * Go to `[your public IP address:port number]` in your web browser!
    * You can see your public IP address in the AWS EC2 Management Consol page also. Select the instance and see the description tab. It seems like a `12.34.56.234`.
    * So, if your public IP is 12.34.56.234 and your port number is 8888, then your notebook address is `http://12.34.56.234:8888`.
    * Type your password! Then you can see your home folder through the jupyter notebook.
