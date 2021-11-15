# Uploading WordPress theme updates via SVN on Mac
Step by step tutorial for uploading WordPress themes using SVN on Mac

## About
Themes authors can now update themes using SVN. This tutorial provides the steps to update WordPress themes using SVN on Mac. 

## Background
Mac includes .DS_Store and __MACOSX when compressing files. They are hidden files and often triggers an error if they are not removed prior to the Zip upload.  By uploading using SVN, Mac users no longer need to compress files and can remove hidden files/folders effortlessly. 

## Instruction

(1) Create a copy of repository on your local machine.

 ```
 svn co https://themes.svn.wordpress.org/NameOfYourTheme/
 ```
