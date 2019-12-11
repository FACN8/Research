#   <center>***Command Line***


### What does command line do?
<p style="font-size:18px">
The command line is a text interface for your computer. It's a program that takes in commands, which it passes on to the computer's operating system to run. From the command line, you can navigate through files and folders on your computer, just as you would with Windows Explorer on Windows or Finder on Mac OS.
</p>
<iframe style="margin:0 auto; width: 100%;border-color: transparent;" src="https://giphy.com/embed/C4NdKtRaQE9m8" width="400" height="250" allowFullScreen></iframe>
<br>

 # <center>How to Beautify your Terminal?</center>

###    Couple of Easy Steps:
<p style="font-size:18px">
1) Right click on your Terminal - Preferences<br>
2) On Global you can change colors, Appearance.
<div style="font-size:17px">

* **On Profile**: Click on General - 'untick use the system fixed width font' choose MonoSpace.
* **color**: background color - change it to your preference.
* **Background**: transparency recommeneded 0.8.

Type in terminal:
```ba    
$ sudo apt install fonts-powerline.
```
```ba  
$ nano .bashrc
```
Paste everything from:
https://raw.githubusercontent.com/ChrisTitusTech/scripts/master/fancy-bash-promt.sh
over write ^0 (by clicking the crtl+shift+O)
```ba  
$ exit
```
```ba  
$ clear
```
then re-launch terminal

---

</p>

<div>

Before             |  After
:-------------------------:|:-------------------------:
![](https://i.imgur.com/eY9UhsH.png)  |  ![](https://i.imgur.com/kRVUIWD.png)
 
 </div>


## **Package Manager: Install**
We can use Package Manager for Windows to install and remove packages.

To install specific version of package we use "apt-get" command  in Ubuntu. 
```b    
sudo apt install <package_name>
sudo apt install <package_1> <package_2> <package_3>
```
![](https://files.gitter.im/LinaQh95/frAm/install.png)


