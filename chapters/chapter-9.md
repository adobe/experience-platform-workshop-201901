# Chapter 9. Technical: Stream in Data via Launch

## Learning Objectives

- Learn how to integrate Adobe Experience Platform Launch onto a webpage
- Create Launch rules to stream data to Experience Platform

## Lab Resources

- Launch URL:

## Lab Tasks

- Deploy webpage on local server
- Create Launch property and add streaming endpoint to webpage
- Create data element and rule to stream a data beacon into Experience Platform
- Observe the beacon firing, and landing in Experience Platform

---

## Story

 

---

## Steps

1. create SPA
2. open launch at https://launch-demo.adobe.com
3. login, go to SPP 1 org
4. click "new property"
5. name is "SPP App Property - firstinitial/lastname"
6. Platform = web. Domain = URL to SPA. SAVE and Open
7. homepage
8. go to extensions. catalog. add experience cloud
9. add experience platform. create streaming endpoint. "Launch Streaming Endpoint - firstinitial/lastname", source ID = "Launch-firstinitial/lastname" - SAVE
10. select the endpoint, then SAVE
11. go to Environments, select "Development", click the box
12. copy script tag and place in header of SPA
13. go to Publishing and add new library. name "wetravel" and environment "Development"
14. click "add all changed resources"
15. save and build for development, should appear
16. data elements - create new data element. name = "Get ECID"
17. Custom code -> copy paste 
	if(typeof Visitor=="function")
	{
  		var visitor = Visitor.getInstance('DDF07AE95C411FED0A495C2A@AdobeOrg');
  		return visitor.getMarketingCloudVisitorID();
	} else return '';
18. 


### Deploying webpage to your machine


### Setting up Adobe Launch

### Streaming a Launch data beacon into Platform

---

### Navigate

**Previous:** Chapter 8 - [Technical: Query the Data](chapter-8.md)
