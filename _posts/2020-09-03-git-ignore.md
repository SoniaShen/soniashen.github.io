Ignoring directories in Git repositories:
web link: https://stackoverflow.com/questions/343646/ignoring-directories-in-git-repositories-on-windows#:~:text=If%20you%20want%20to%20maintain%20a%20folder%20and,included%20in%20your%20repository.%20%24%20git%20add%20path%2Fto%2Ffolder%2F.gitignore

i.e.
If you want to maintain a folder and not the files inside it, just put a ".gitignore" file in the folder with "*" as the content.
---
But .gitignore will be included in your repository.
$ git add path/to/folder/.gitignore
---
If you add an empty folder, you receive this message (.gitignore is a hidden file)
---
The following paths are ignored by one of your .gitignore files:
path/to/folder/.gitignore
---
Use -f if you really want to add them.
fatal: no files added
---
So, use "-f" to force add:
$ git add path/to/folder/.gitignore -f

 =====> =====> =====> =====> =====> =====> 


$ cat ./nsds/inuksuk-model/.gitignore
.intermediate/
/Output_Models/

$ cat ./nsds/ft4p-nsds/.gitignore
**/ft4p.properties
**/ft4p.xml

$ cat ./nsds/inuksuk-cba-esm-installer/.gitignore
vwcg-nsds-esm-config/src/main/resources/esm/ova-build-files/pxeboot.qcow2
vwcg-nsds-esm-config/src/main/resources/esm/packages

 ----- ----- -----
$ cat ./.gitignore
# Common editor swap-files
*.bak
cp_nsds.txt
Keystore_dir/
*.swo
*.swp
*~
.#*
\#*#
*.jar
.TITAN_properties

# Project files
*.iml
.cdtproject
.classpath
.idea
.idea/
.project
.pydevproject
.settings/

# Everything in tmp directory and below
tmp/

# t3Lib temp file
testcase_data.tmp

# eclipse default compilation directories
# exclude certain source directories
bin/
!mmas/bin
!dev/bin
!health/bin

# Maven target folder
target/
applications/

# binary directories
!/h2s-cba-healthcheck/src/main/scripts/home/health/bin/
!/h2s-sdp/SDPFiles/DeployFiles/jbcp6/traffic/mmas/bin/
!/inuksuk-bumper-sdp/SDPFiles/DeployFiles/jbcp6/traffic/mmas/bin/
!/inuksuk-cba-healthcheck/src/main/scripts/home/health/bin/
!/inuksuk-sdp/SDPFiles/DeployFiles/jbcp6/traffic/mmas/bin/
bin-*

# Wireshark file
*.pcap

# downloaded rpm
sshd_config_sftp_filem-1.0-2.x86_64.rpm

# ctags file
.tags

# sshfs fuse files
.fuse*

# TG result files
*.csv

# Kate editor temp files
*.kate-swp
 ----- ----- -----



 =====> =====> =====> =====> =====> =====>
Learn Git -> .gitignore    [suggested web site: atlassian Bitbucket]
web link: https://www.atlassian.com/git/tutorials/saving-changes/gitignore#:~:text=ignored%20-%20a%20file%20which%20Git%20has%20been,caches%2C%20such%20as%20the%20contents%20of%20%2Fnode_modulesor%20%2Fpackages

i.e.
git add / git commit / git diff / git stash / .gitignore


















