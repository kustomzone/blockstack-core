resolver
=======

## Installation:

Notes on installing the resolver. 

## For quick deployment:

```
pip install -r requirements.txt
./runserver
```

To deploy on Heroku:

```bash
heroku create
heroku addons:add memcachedcloud
git push heroku master
```

## Detailed Instructions:

###1. resolver requires memcached:

###Linux:
```
sudo apt-get install memcached libmemcached-dev zlib1g-dev
```

Before installing pylibmc (listed in requirements.txt) install the above packages.

Install pybitcoin:
```
pip install pybitcoin
```

------------------------------------------------------------------
###Mac OS X:

Easiest way is to make use of brew

brew can  be installed by:
```
	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)”
```
After installation:
```
brew install libmemcached
```
libmemcached dependencies: 
		```
		memcached : brew intall memcached 
		libevent(should automatically install) :  brew intall libevent 
		```

------------------------------------------------------------------
###2. running memcache:
/usr/local/opt/memcached/bin/memcached


an easier way to launch memcache is to use Lunchy:

Lunchy is a gem that simplifies the command line interface to launchctl. To install Lunchy, do

gem install lunchy
```
  1. $ mkdir ~/Library/LaunchAgents
  2. $ cp /usr/local/Cellar/memcached/$version/homebrew.mxcl.memcached.plist ~/Library/LaunchAgents/
  3. $ lunchy start memcached
  4. $ lunchy stop memcached
```

------------------------------------------------------------------
###3. Ensure you have python 2.7 and python development headers installed:

on linux:
```
	sudo apt-get install python2.7-dev
```

on Mac:
	
	On mac headers are automatically installed during the process of python installation. Python 2.7 can be installed as follows.
  	```
  	1. brew install python
    2. brew link python

    3. ensure you GCC installed:
    	GCC can be obtained by downloading XCode, the smaller Command Line Tools (must have an Apple account) or the even smaller OSX-GCC-Installer package
    ```
	Comprehensive guide to installing python on mac:
	
		http://docs.python-guide.org/en/latest/starting/install/osx/#install-osx



------------------------------------------------------------------

###4. pip install pybitcoin