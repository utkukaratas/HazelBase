# hazelbase

This is going to be a polyglot backend service similar to Firebase/Parse. 

# Technical Details

* The core will be a Java/Clojure web server. 
* Hazelcast will provide the caching and task execution and message queue layer. 
* Persistence layer will be Postresql or SQLite.

# Intended audience

* Serial freelancers who copy/paste from their old Django/Rails/Node projects to hit the ground running on their new projects.
* Developers who want to get rid of depending on Firebase, Auth0, AWS Cognito, etc... 
