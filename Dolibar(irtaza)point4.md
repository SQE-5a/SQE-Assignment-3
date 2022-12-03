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

