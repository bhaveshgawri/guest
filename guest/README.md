# guest
>a faster and better alternative for chrome incognito mode

### What it is?
* python script to start an anonymous google chrome session from terminal
* runs the chrome using chromedriver
* deletes the data(everything) after the browser is closed.

### How should I use it?

* First download the  [chromedriver](https://chromedriver.storage.googleapis.com/index.html?path=2.28/) and do following:
```
$sudo cp ~/Downloads/chromedriver /usr/bin/
$sudo chmod +x /usr/bin/chromedriver
```
* You need to install Selenium
```
sudo pip install -U selenium
```
* Download the script, copy it to /usr/bin and give it +x permission.
```
$sudo mv ~/Downloads/guest /usr/bin
$sudo chmod +x /usr/bin/guest
```
to run it use and it will start an anonymous session.
See help for more options.
```
$guest
$guest --help
```

### Other Prerequisites
You must have latest version of [google-chrome](https://www.google.com/chrome/browser/desktop/index.html) installed.
