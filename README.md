# Uploading WordPress theme updates via SVN on Mac

## About
Themes authors can now update themes using SVN. This tutorial shows the steps to update WordPress themes using SVN on Mac. 

## Background
Mac includes `.DS_Store` and `__MACOSX` when compressing files. They are hidden files and often trigger an error if they are not removed prior to upload. SVN allows Mac users to remove hidden files and streamline automation. 

## What you will need
- MacOS 
- [VS code](https://code.visualstudio.com/Download)
- [SVN module](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm)

To check whether you have svn installed, type `svn --version` in terminal. 


## Instruction
(1) Create a copy of the repository on your local machine. Replace `/NameOfYourTheme/` with your theme name. 

You can search and find the exact name of your theme (e.g. hyphen, undersocre) at this link. https://themes.svn.wordpress.org/

 ```
 
 svn co https://themes.svn.wordpress.org/NameOfYourTheme/
 
 ```
 

(2) The next step is to create a new directory and copy all theme files, including the history from the current version of the theme. 
In the example below, we are creating a new directory `1.0.2`, and copying all files from the version `1.0.1`.

```

svn cp 1.0.1 1.0.2

```

Note: Updates MUST be stored in a directory with the version number as the directory name. For example, if your current theme is `1.2.3`, the new directory MUST be `1.2.4`.   e.g. `/NameofYourTheme/1.2.4`

Note: To get the full path to the current version of your theme using VS code on Mac, you can simply drag the folder into the terminal area to get the full path. 

(3) Add the new directory to a local working group. Replace `1.0.2` with the new directory you just created. 

```

svn add 1.0.2

```

(4) Make changes to your theme.  Make sure to update the version number on Style.css, and the Changelog on readme.txt 

(5) Once you are happy with updates, you are ready to submit the update. 
First, make sure to remove `.DS_Store` hidden file. 

```

find . -name ".DS_Store" -print -delete

```

(6) Then remove __MACOSX folder.

```

rm -R __MACOSX

```

(7) Finally you are ready to commit.

```

Svn commit -m “Fix typo on readme.txt”

```

Note: once you commit, absolutely no way to change or modify what you just commit. If you find any mistakes including a small typo, the only way to fix is to start over from step 2, create a new directory, and upload again. 

## What to expect next
Once you successfully upload the new update, you will receive a confirmation email from WordPress.org. It may take some time to reflect on the WordPress.org directory. 


## Getting help

If you find any issues or questions, please create a new [issue](https://github.com/TeBenachi/Uploading-WordPress-theme-updates-via-SVN-on-Mac/issues). 


## Resources
WordPress theme review process is making steady progress towards automation. Check out the following links for the ongoing efforts and upcoming changes. 

- Oct 14, 2021 - [Theme tools and requirements recap](https://make.wordpress.org/themes/2021/10/14/theme-tools-and-requirements-recap/)
- Sept 13, 2021 - [Theme upload survey results & next steps](https://make.wordpress.org/themes/2021/09/13/theme-upload-survey-results-next-steps/)
- Mar 27, 2021 - [Chat with Matt about the future of theme repo](https://make.wordpress.org/themes/2017/03/27/chat-with-matt-about-the-future-of-theme-repo/)
- Mar 17, 2021 - [Next Steps on Themes and Reviews](https://make.wordpress.org/themes/2021/03/17/next-steps-on-themes-and-reviews/)
- Feb 24, 2021 - [Meeting Notes | Matt Josepha and Theme Team](https://make.wordpress.org/themes/2021/02/24/meeting-notes-matt-josepha-and-theme-review-team/)


Thank you [@dd32](https://github.com/dd32) for reviewing!




