Step 1 - Right Click Pom.xml -> Maven Install

Step 2 - Start microService
java -jar target/MavenDropWizardSample-0.0.1-SNAPSHOT.jar server tasklist-service.yml

Step 3 - Test Service
http://localhost:18080/task-list?contains=java