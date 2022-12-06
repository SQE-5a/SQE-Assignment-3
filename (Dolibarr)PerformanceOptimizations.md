# Usage Of Cache  
Caching is a temporary storage mechanism that allows websites to load information faster. Instead of accessing the database directly, the website will access the cached version and pull the necessary information from the server memory.
Mostly it is used when websites have static attributes like header footer layout,etc.

MemCached Allows Dolibarr to increase speed . Dolibarr use this cache to store result of redundant operation like IO used for reading language files. According to platform, speed increase can be between 20% and 40%.
This module is a technical module. As soon as setup is done, Dolibarr use the cache server when it thinks it's necessary. There is no other things to do.

The following screenshot show you a performance comparison, done with BlackFire, with and without the module. As we can see, the gain (59ms faster for a total of 152ms, so 25% faster) is mostly on the step to load the language files (already in cache, 56ms for this step in function Translate::load).  

<img width="907" alt="usageOfCache" src="https://user-images.githubusercontent.com/113935723/205513813-40b730b4-8a99-4d8e-8443-fa80f171db98.png">  
## Link:  
https://wiki.dolibarr.org/index.php?title=Module_MemCached  

# CDN  
You can have the fastest servers, but if you distribute your page across geographic locations, it can't be fast. In our cloud, we use the fastest CDN solution provided by Cloud.  
Dolibarr is also giving their users option to use CDN facilities with dolibarr at CloudClusters by following procedure and preConditions:  
<img width="959" alt="cdn" src="https://user-images.githubusercontent.com/113935723/205514373-440cf40c-50aa-4569-b00c-6d741f967bdf.png">  

# Lazy Loading  

Lazy loading is a way used to prevent or delay the loading of non-critical resources until they are needed.  
When you open first page then there is no need to load the 3rd page ,when further load will be needed like you go to 3rd page then 3rd page loading should be started.  
You can use this mechanism for different types of resources, but in the case of images, our goal is to lazily load everything that is not visible to the user within the initial viewport.

Use the loading="lazy" attribute to load an image lazily.But they have not 


# PWA  
Progressive Web Application (PWA) is a type of web app that can operate both as a web page and mobile app on any device.The web app manifest is a file you create that tells the browser how you want your web content to display as an app in the operating system. The manifest can include basic information such as the app's name, icon, and theme color; advanced preferences, such as desired orientation and app shortcuts; and catalog metadata, such as screenshots.It also uses service workers.Its configuration is done mostly in manifest.json file .  
<img width="947" alt="PWA" src="https://user-images.githubusercontent.com/113935723/205865539-8a11b695-6df7-448c-bc66-87e7be5d0cab.PNG">  


# Local Storage
 This lets you persist data for long-term storage, save sites or documents for offline use, retain user-specific settings for your site.
Closing the browser will not affect the data in any way – it stays there unless you delete it.
