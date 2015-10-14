.. post:: Oct 14, 2015
   :tags: ablog, sphinx
   :author: Ian Edwards

   
Installing ABlog on Windows
===========================

A few notes on the method I used to get ABlog running on Windows.

.. note::
  Git is installed seperately - Github Desktop is an easy way to install git
  and powershell and it will automatically know the ssh keys for your github
  account.

#. Install Miniconda python 2.7 64-bit for windows (miniconda is conda without
   the included 100 standard packages).

     http://conda.pydata.org/miniconda.html

   I did not add this python to the PATH etc - so this install is completely
   stand alone. Installed in /Users/user_name/Miniconda.

#. Pip should be  installed as standard in Python 2.7.9+ but oddly is not in 
   the Scripts folder in the miniconda install, therefore I downloaded 
   and ran get_pip.py

     http://stackoverflow.com/q/4750806/1895018

#. Install ABlog using pip install -U ablog

     http://ablog.readthedocs.org/

   This all ended up the the Scripts folder, including ablog.exe 
   (possibly because this was the current folder when I installed?)

#. Create a ablog.cmd script in your git folder (this can then be called using
   "..\ablog.cmd"). The script has the following contents:
  
     C:\\Users\\guest_user\\Miniconda\\Scripts\\ablog.exe %*

#. ABlog start, ABlog build, ...
   My local blog ended up in:
     file:///C:/Users/guest_user/git/bitblog/_website/index.html
  
#. If publishing online with github pages, ablog can take care of deployment
   with:

     ablog deploy -p ../username.github.io/