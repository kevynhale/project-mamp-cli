## project-mamp-cli
CLI tool for mac to manage free MAMP projects through the cli.

To use these tool you will need to make sure to properly set up your directories. Make sure to point the script to the location of the management scripts in MAMP:
 \n 3 #set static files.
  4 startApache='/Applications/MAMP/bin/startApache.sh'
  5 stopApache='/Applications/MAMP/bin/stopApache.sh'
  6 startMysql='/Applications/MAMP/bin/startMysql.sh'
  7 stopMysql='/Applications/MAMP/bin/stopMysql.sh'
  8 ROOT='/Applications/MAMP/conf/apache/httpd.conf'
  
Next, you will need to set up a directory and file to store you project data. The project data will simply contain a a list of the project name and directory.
  
  9 HOME='' #set Home Directory
 10 LISTDIR="$HOME/Applications/project" #create a directory to store the project list in
 11 LISTFILE="$LISTDIR/project.list" #create a file to store the projects in.

Place the project file in /usr/bin so the script can be called from anywere in the terminal

Here are the commands:

- Add a new project

project add #projectName #projectDirectory

- See current list of projects

project list

-- Delete a project

project remove #projectName

-- Select a project. This sets this project directory as the selected project in MAMP, and restarts apache and mysql.
-- It also opens up the project directory in sublime.
-- Currently on line 179, any custom scripts can be added when selecting your project. i.e, running gulp/grunt or other processes.

project select #projectName


