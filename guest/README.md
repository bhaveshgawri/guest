# guest
>a faster and better alternative for chrome incognito mode

### What it is?
* 3 lines of python code.
* runs the chrome using chromedriver
* deletes the data(everything) after the browser is closed.

### How should I use it?

First download the  [chromedriver](https://chromedriver.storage.googleapis.com/index.html?path=2.28/) and do following:
```
$sudo cp ~/Downloads/chromedriver /usr/bin/
$sudo chmod +x /usr/bin/chromedriver
```
Now, there are 2 ways:

* Download the binary from [here](https://drive.google.com/open?id=0B1o2cfjSr08fS0xlN2NhcERYSVU), 
copy it to /usr/bin and give it +x permission.
```
$sudo mv ~/Downloads/guest /usr/bin
$sudo chmod +x /usr/bin/guest
```
to run it use
```
$guest
```
and it will start an anonymous session.

Another way:

* Get the code, install selenium,
and run the code as a python script.
```
$sudo pip3 install -U selenium

```
to run it
```
$python3 ~/path_to_script/guest.py
```
this will also start an anonymous session.

### Other Prerequisites
You must have [google-chrome](https://www.google.com/chrome/browser/desktop/index.html) installed.
