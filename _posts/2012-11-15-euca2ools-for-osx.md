---
title: euca2ools for OS X
tags: eucalyptus, euca2ools, OS X
---

<small>euca2ools are written in python. You might want to use a
python virtual environment for this. Figure this out on your
own</small>

Install stuff

1. Go to a folder for downloading and making
2. `wget https://github.com/eucalyptus/euca2ools/archive/2.1.1.zip`
3. `unzip 2.1.1.zip`
4. `cd euca2ools-2.1.1/`
5. `python setup.py build`
6. `sudo python setup.py install`
7. `sudo pip install boto` to install boto dependency
8. `sudo pip install m2crypto` to install m2crypto dependency
9. Remove the folder for downloading and making

I recommend moving or symlinking your downloaded credentials file to
"$HOME/.eucarc". This is a default location for euca2ools to look
for configuration info. If you don't use "$HOME/.eucarc", you have to
change the eucarc file to set the EUCA_KEY_DIR correctly (since there
isn't a functioning `readlink -f` on OS X), and then source eucarc.

You're done. Try `euca-describe-images`.

<small>A similar and useful guide for this is on <a
href="http://polibyte.com/blog/installing_euca2ools_on_os_x">polibyte</a>.</small>

