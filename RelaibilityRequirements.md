# Auto Scalability
With the growing popularity of Vue Storefront,they continue to aim high. We’d like to become the industry standard for eCommerce frontends.  
This means duplicating the leadership status we’ve gained in the Magento PWA world across all other platforms, including custom backends.   
In order to do this, it is not enough to develop just a single product.Vue Storefront is, therefore, an ecosystem of developers' tools enabling fast and nimble implementations of modern commerce storefronts.
Cloud-native infrastructure enables to handle dynamic traffic peaks by automatically adding or removing resources.  
This model leaves merchants confident that their webshops always meet current demands in terms of organic traffic.
<img width="948" alt="scale" src="https://user-images.githubusercontent.com/113935723/205465733-801c4c7f-e9a7-4740-bcce-d0197ae69d8e.png">   

Vue StoreFront is a decoupled headless eCommerce solution you can leverage with benefits including a PWA and 100% offline support.   
In this talk, They covered how Vue StoreFront can help you build more resilient eCommerce applications.  
## Link:
https://speakerdeck.com/lauragift21/scaling-your-ecommerce-with-vue-storefront

 # Load Balancing
 <img width="650" alt="loadBalancing" src="https://user-images.githubusercontent.com/113935723/205466219-6da5b844-ffbe-443b-ab50-ea560f7892ca.png">  
“Vue Storefront is a headless and backend-agnostic eCommerce Progressive Web App (PWA) written in Vue.js” – quoted from their site. In theory,   
you can transform your magento to a PWA which should be able to perform like a native mobile app. So, if you want to make your Magento (especially, Magento 1)  
faster without spending too much money for the server upgrade, or;   
spending too much time upgrading to Magento 2.
AWS has a good reference on how to implement Magento on its cloud service (see pict above). It’s pretty standard architecture for Magento, though: load balancer (with optional autoscaling group),  
and the load balancer has several availability zone with its own independent services (multiple web servers, one single database, and one redis instance).  

However, when you look at Vue Storefront architecture, there’s not so much difference. Vue Storefront will still use Magento to get what it needs via Magento API,  
then store the information in its own data storage.  This way, Vue Storefront will be the first server behind your load balancer that will process requests from the website’s visitors. Then, it will check on its storage   (which is a lot faster because it uses no SQL) of the information that it needs, and return it back to your visitors. If the information doesn’t exist,   it will finally request that information via Magento API. 

They are using Aws services and 

 # Automatic deployments

  Vue Storefront Cloud is a blazing fast cloud infrastructure fitted to Vue Storefront. Our cloud isn't only a compute power.  
  We prepared custom, intelligent algorithms to optimize and speed-up your VSF instance and provide your customers the best eCommerce experience.
  cloud-native compute power on Google Cloud Platform. Our images, containers, tools use Kubernetes. Kubernetes is the best orchestration tool in the world, made by Google. Where can those work better?

CDN - the last mile to the customer is the most important. We can have the fastest servers, but if you distribute your page across geographic locations,  it can't be fast. In our cloud, we use the fastest CDN solution provided by Cloud.  

server-side rendering - Vue Storefront Cloud is fitted to VSF.They provide server-side rendering for cache and distribute content across geographic locations.  No more lost the time to fetch API, prepare layout and distribute to each customer separately.  

instant eCommerce page load.


  Each deployment is managed via storefrontcloud-cli and the GitLab repository. We are using a fully automatic deployment   flow with the evidence of changes (git-log) and a simple restore process in case of any failure.  

## CLI access to env:
The platform is accessible and manageable via the storefrontcloud-cli tool. It’s a dedicated tool to manage the Kubernetes cluster and Vue Storefront deployments, backups, and logs.

# Fault tolerance
## Monolithic
If one part of the application fails with a monolith, the entire system may go down.

## Microservices
Microservices are more fault-tolerant than monoliths because a single service can continue working even if another service fails.  

Key microservices principles:  
1. They are built around business capabilities: Microservices won’t restrict themselves from adopting appropriate tech stacks or a backend database storage most suitable for solving specific business problems. They can adapt on a per-case basis.  

2. They have a single responsibility: This forms a part of the SOLID design pattern. It simplifies any microservice by delivering only one core functionality. So, if you need five functionalities, you need five microservices with five separate databases.  

3. They are designed with failure cases in mind: It will not affect the entire system when one microservice goes down. This is a crucial reason why they are increasingly popular in eCommerce businesses. All other functionalities remain intact when one module fails.  
     
  And Vue Store Front is using micro services So in that way,Vue Store Front is handling fault Tolerance,etc.


# RecoverAbility:
Their cloud support team provides daily backups, which makes testing new solutions safely. You can freely reach out for the newest solutions, battle-test them, and then decide if you want to keep or remove them.  
Daily backups we deliver by default make your business consistency perfectly secured.
Also they have provided options users to recover like:

useForgotPassword feature composable can be used to:
 
generate reset password token  
 
set new password using token  
So in these ways ,they are acheiving recoverAbility.  
<img width="944" alt="backup" src="https://user-images.githubusercontent.com/113935723/205467109-084966e6-913d-443a-b18c-242eec1795ca.png">  
That's All about Relaibility Requirements of Vue StoreFront open source project.
