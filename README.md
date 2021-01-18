**The Minimal MediaWiki Deployment
* Install the mediawiki image using helm . 
* 1: helm upgrade --install mediawiki -f mediawiki/values mediawiki
* 2: check loadbalancer ip by executing: kubectl get svc svc-mediawiki
* 3: Install the mariadb Database executing :
* helm upgrade --install mediawiki-db -f mediawiki-db/values mediawiki-db
* 4: We can check the clusterip service running. 
* 5: To access db username and password we can decode the base64 secrets. 
* 6: Now we can configure our website with our mariadb instance. db-hostname should be "svc-mediawiki-db" and previously obtained username and password.
* 7: After configuring we can Download the Localsettings.php and now we need to share it with our cluster.
* 8: To test we can just copy the settings file using kubectl cp relative_path pod:/var/www/html/Localsettings.php
