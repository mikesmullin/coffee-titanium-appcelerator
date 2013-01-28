# Coffee + Titanium Appcelerator (CLI)

[Titanium Appcelerator](http://www.appcelerator.com/) allows you to write javascript once and compile to _native_ mobile device code (iOS, Android, etc.).
They provide you with a single [Titanium API](http://docs.appcelerator.com/titanium/3.0/#!/api) which gives your javascript access to device hardware (e.g. camera), common functions (e.g. facebook graph api, importing contacts), and common ui.

But I enjoy writing [CoffeeScript](http://coffeescript.org/) more than [JavaScript](http://www.ecmascript.org/docs.php). CoffeeScript compiles to JavaScript.

[Node.js](http://nodejs.org/) is fast. I have enjoyed it for writing many things especially web applications.

I have begun writing a Node.JS web framework called [CoffeeShop](https://github.com/mikesmullin/coffee-shop).

My goal here is to explore how I might make it as easy as possible for
a developer to write once in CoffeeScript and have it build and deploy to web server, mobile app, and stand-alone desktop applications.
Sharing business logic through commonly-defined patterns like Models, and View Templates.
I want [CoffeeTemplates](https://github.com/mikesmullin/coffee-templates) to compile to either .html or .xml and [CoffeeStylesheets](https://github.com/mikesmullin/coffee-stylesheets) to either .css or .tss.

I also despise Eclipse IDE which is what Titanium Studio extends, and want to stick with Ubuntu + GVIM + CLI as my dev environment.

All directions below are for Ubuntu 12.04.

## Install NVM (recommended)
```bash
sudo apt-get remove nodejs npm # if it was installed before this
curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

## Install Node.JS
```bash
nvm install 0.8.15 # the version we're testing with
nvm alias default 0.8.15
```

## Install Google Android SDK
```bash
wget http://dl.google.com/android/android-sdk_r21.0.1-linux.tgz
tar zxvf android-sdk_r21.0.1-linux.tgz
cd android-sdk_r21.0.1-linux
tools/android # wait for gui to appear
# select latest android sdk and choose install and accept all
# setup a new emulator and run it
```

## Install Titanium Appcelerator
```bash
npm install titanium -g
titanium login
titanium sdk update --branch 3_0_X --default
titanium setup
```

## Install CoffeeScript
```bash
npm install coffee-script -g
```

## Install this Hello World app
```bash
git clone git://github.com/mikesmullin/coffee-titanium-appcelerator.git
cd coffee-titanium-appcelerator
npm install
cd static
# make sure android emulator is running before this next step
titanium build --platform android --target emulator --deploy-type development
```

## Resources:
* [Titanium Command-Line Interface](http://docs.appcelerator.com/titanium/3.0/#!/guide/Titanium_Command-Line_Interface_Reference-section-35619828_TitaniumCommand-LineInterfaceReference-Create)
