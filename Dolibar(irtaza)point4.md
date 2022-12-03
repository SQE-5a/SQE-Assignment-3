# Reliability Requirments of Dolibar

## 1- Load Balancing in Dolibar:

As far as i studied the link and answers of serverl people in `Dolibar Forum`
I got to know that ou should be able to install multiple web servers and point 
them to the central DB server. The web servers have to sync their dolibarr 
directory (like drbd/ocfs2) or access a shared medium. If you want to separate 
the data and the software, you should share/sync the directory dolibarr/documents 
at least, as there are the attached files, etc. stored.

Your load balancing should be somehow session aware (sticky session for a certain time or based on cookies, etc.), 
since Dolibarr does not store any session in the DB (only the login time of a user for information).
The session handler seems to be PHP. This means that a switch to another server yields into a new login.


<img width="960" alt="Screenshot_20221203_014423" src="https://user-images.githubusercontent.com/105812482/205432497-50a850a6-da36-4f76-a669-79c6a00bf6d7.png">

## 2- Recoverability in Dolibar

This is the simplest way to make your backup, and in addition all your backups will be stored on server and will be listed, so that you can retrieve any version anyday.

If you use a recent enough version of Dolibarr, just log into Dolibarr with an administrator account (only admins can use system tools).

Then go to Home -> System tools -> Backups. Choose your options for your backup (you can keep all default values).

Alternative: the default method MySQL Dump (mysqldump) also needs that you have access to the mysqldump binary in execution on your server. If you are on a shared host that disable the mysqldump usage, you can try other method called MySQL Dump (php). This method is not guaranted at 100%, so please try it first by yourself by making a backup and then restoring it on a local non production server to check that your data is correctly saved.


Link: https://wiki.dolibarr.org/index.php?title=Backups

<img width="960" alt="Screenshot_20221203_014857" src="https://user-images.githubusercontent.com/105812482/205432671-fa5c4029-c53f-419d-a240-12b858a64a58.png">

### Using mysqldump
If you prefer a manual mode, you can also use the backup tool designed for your database. With Mysql, the command to backup your database into a file is :

`mysqldump -u user -pyourpass --result-file=mysqldump_databasename_version_date.sql databasename`



