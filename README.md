# Check Point CloudGuard AppSec demo
 
 This is a simple docker-compose environment for deploy a Check Point AppSec embedded nano-agent demo.  
 It will deploy 5 containers, an NGINX reverse proxy, an agent-container (the nano-agent), OWASP JuiceShop app, bWAAP app and DVWA app.
 The reason to deploy all is to make you use the app where you feel confortable to launch attacks.

You will have two ways to access the stack apps:  
* Port 80: Protected by AppSec  
* Port 3000: Direct to JuiceShop (unprotected)  
* Port 3001: Direct to bWAAP (unprotected)
* Port 3002: Direct to DVWA (unprotected)
  
## Instructions:
 
* Clone the repository
* From a machine with docker and docker-compose installed, run:  
`  export TOKEN=<your agent token>`  
`  docker-compose up `  
__Insert awesome demo here :)__  
`  docker-compose down `  
 


> Notes: 
> The NGINX config requires you to provide a host header otherwise you'll get a 404. The host header (eg, entry in your host file) should be *http://juiceshop.cloudguard.test/* *http://bwaap.cloudguard.test/* *http://dvwa.cloudguard.test/* the easier way is to modify your host file to point to the IP address of the machine running Docker
> There are two ways to run docker compose: `docker-compose` and `docker compose`. Using `docker compose` (with a space, not a hyphen) is 'experimental' from a Docker perspective and seems to decide on its own value for IPC configuration and breaks this setup. Use `docker-compose` please :).
> I you want to learn more about the Reverse Proxy, you can see the 'default' file inside the /nginx-reverse-proxy folder, this is mounted to the container to provide Host Rules and Ingress Routes
