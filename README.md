# Undeploy-Proxy
This script/jar can be used to undeploy the list of proxies which does not have traffic. The list must be provided as the input for this jar (this list can be got from another bundle - apigee bundle reaper https://github.com/apigeecs/ApigeeBundleReaper ) 

----
Execution steps
----
-Download the jar file

-In command prompt traverse to the specific path of downloaded jar (make sure to stay on internal network when running the below command for on-prem apigee)

run $java -jar UndeployRevisions.jar username password protocol domain org environment filepath

example: java -jar undeployRevisions.jar username password http 10.158.150.179:8080 zatlab zlab01 C:/Users/username/Desktop/zlab01ProxyList.txt

-To store the output to a file use the following command (make sure to stay on internal network when running the below command)

$java -jar UndeployRevision.jar username password protocol domain org environment filepath > /path/filename.txt

example: java -jar undeployRevisions.jar username password http 10.158.150.179:8080 zatlab zlab01 C:/Users/username/Desktop/zlab01ProxyList.txt > C:/Users/username/Desktop/zlab01Output.txt

-Description for the arguments being passed in above command

    username and password -> credentials used for apigee login
    protocol -> https/http
    domain name -> api.enterprise.apigee.com for saas, if on prem provide the on prem domain name
    org -> organization for which the undeployment as to be done
    environment -> the environment for which the undeployment must be done
    filepath -> this is the path of the file which contains the list of proxy names for which we have to undeploy the proxy revision. Specify full path for the file. for example: C:\Users\...\Desktop\proxylist.txt

Repeat this by passing the environments and the text files corresponding to environments to undeploy all the revisions without traffic across all the environments.

