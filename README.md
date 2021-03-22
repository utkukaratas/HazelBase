# HazelBase

This is going to be a polyglot backend service similar to Firebase/Parse/Auth0. 

# Intended audience

* Serial freelancers/small teams who copy/paste from their old Django/Rails/Node projects to hit the ground running on their new projects.
* Developers who want to get rid of depending on Firebase, Parse, Auth0, AWS Cognito, Okta etc... 
* Younger generation who want to spend as little time as possible on backend work.

# Technical Details

* The core will be a Java/Clojure web server. 
* Hazelcast will provide the caching and task execution and message queue layer. 
* Persistence layer will be Postresql or SQLite.

