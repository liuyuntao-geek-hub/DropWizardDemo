Step 1 - Right Click Pom.xml -> Maven Install

Step 2 - Start microService
cd E:\java\Maven\EclipseWorkSpace\MavenDropWizardSample
java -jar target/MavenDropWizardSample-0.0.1-SNAPSHOT.jar server tasklist-service.yml

Step 3 - Test Service
http://localhost:18080/DropWizard/task-list
http://localhost:18080/DropWizard/task-list?contains=java

http://localhost:18080/DropWizard/employee?empno=1


***************************************
	Interact with JavaScript
****************************************

Step 1 - Add code 
	http://srikanthtechnologies.com/blog/java/rest_service_client.aspx

	

Step 2 - start the service

	cd E:\java\Maven\EclipseWorkSpace\MavenDropWizardSample
	java -jar target/MavenDropWizardSample-0.0.1-SNAPSHOT.jar server tasklist-service.yml


Step 3 - Manual test the service employ function works

	http://localhost:18080/DropWizard/employee?empno=1
	http://localhost:18080/DropWizard/task-list

Step 5 - In eClipse: AngularJSSampleProj/WebContent
	- Create 21_DropWizard_javaScript.html
	- Run the above on the server
	= This will test the code work on local
	= Next step is to deploy it to the webLogic Server

Step 6 - Create JDeveloper Project for web service (Open an web Project already created)
	E:\java\workspace11117\NewStudy\ServletLog4J

---------------------------------
Action 1 - Create Servlet = Hello World
	New Application -> Generic Appliation 
	Application: ServletLog4J 
	Project: ServletLog4JProj


Action 2 - Create HTTP Servlet
	new -> Web Tier -> Servlets => HTTP servlet => Servlet 2.5 => ServletLog4J
	Package: com.servlet.sample
	implement Methods: service()
	Name: servletlog4j
	URL: /servletlog4j
	Web.xml will be created automatically

Action 3 - Test run
	Deploy -> Deployment Profiles -> War File: servletLog4JProfile
	
http://192.168.1.21:7004/ServletLog4J-ServletLog4JProj-context-root/servletlog4j
---------------------------------------------

Step 7 - Create the DropWizardLocalTest.html file in Web Content folder

Step 8 - Search: Project Properties -> JAVA EE Application => find the webroot

http://192.168.1.21:7004/ServletLog4J-ServletLog4JProj-context-root/DropWizardLocalTest.html

Step 9 - Start Linux WebLogic all servers
	- only need to start the Admin server:
	http://192.168.1.21:7001/ServletLog4J-ServletLog4JProj-context-root/servletlog4j
	http://192.168.1.21:7001/ServletLog4J-ServletLog4JProj-context-root/DropWizardLocalTest.html

Step 10 - Not working because the security setup - Fix:

http://stackoverflow.com/questions/5005960/xmlhttprequest-status-0-responsetext-is-empty
----------------------------------------------------
For Firefox, you have to enable it in your config settings
signed.applets.codebase_principal_support = true

Then add something like this to your XHR open code:
  if (isLocalHost()){
    if (typeof(netscape) != 'undefined' && typeof(netscape.security) != 'undefined'){
      netscape.security.PrivilegeManager.enablePrivilege('UniversalBrowserRead');
    }
  }

For IE, if I remember right, all you have to do is enable the browser's Security setting under "Miscellaneous → Access data sources across domains" to get it to work with ActiveX XHRs. 
----------------------------------------------------
