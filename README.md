extract-mbz
===========

Extract content from Moodle backup files (.mbz)

This code is a fork from  https://github.com/varlokkur/extract-mbz

## Requirements:
Python >= 3.6 <br>
python package: python-slugify. Best to install by running `pip install -r requirements.txt`

## Usage:

Create a directory (folder) for your archive and place your .mbz file in it.
If you choose to relocate the python program files from your downloads folder to a new location, 
make sure the tachyons.css file is still in the same directory as your copy of the extract-mbz.py file.

`python extract-mbz.py <full-path-to-your-mbz-file>`

If successful, you will see a new folder created in the directory where your archive is, with the same title 
as the original .mbz file.

Within this new folder, look for the subfolder titled <shortname-of-your-course>. This subfolder contains all 
the documents from the course, along with a html document containing the all the links and text from that course.
If you're sharing the course contents with someone else and don't want to include the extraneous xml files, you can 
send just this <shortname-of-your-course> subfolder without missing any files or breaking the links in the html document.
    
For Command line help - use a question mark as the parameter - <path-to-python-program-if-needed>python extract-mbz.py ?  

## Technical Background:
As already stated, I've been hacking at this so far, and not using detailed specifications to develop this tool. The proof of concept showed me how to get files and I figured out how to get URLs by looking at the .xml files. This probably won't work for more complex data structures such as grades so we'll need to understand the details of the Moodle Backup process. 

As expected, Moodle uses an xml format to create course backups. The xml files and related documents are compressed in a .zip format archive. One uses any unzip-compatible program to retrieve the contents. 

http://docs.moodle.org/dev/Backup_2.0_for_developers

Information page: https://sites.google.com/a/colgate.edu/dwheeler/Home/extract-mbz

<hr>

#  Update by Noam C
Updated the code to run in Ubuntu 22.04, using python 3.8, on Moodle unknown-version, installed in the Technion on 2022
