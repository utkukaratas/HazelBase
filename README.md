# HazelBase

This is going to be a polyglot backend service similar to Firebase/Parse/Auth0/Okta/AWS Cognito... 

# Pitch

## Problem

You need to get started with an app (web/mobile/...); but first you need to lay the groundwork for "users" before implementing anything app specific.

So the dreaded "user" table in your database and all the basic/boring functionality around that.

### Why is it a problem

Consider what that "basic" functionality is:

* Register users
  * send verification sms's  
  * send welcome emails
    * now you need "workers" (as you can't do these in request/response cycle)
      * your "workers" solution will tell you to run a "message broker" (hello Redis/RabbitMQ)
* Authenticate users
  * Lots of tight secure code. You can't screw up here.
* Lots of other trivia
  * Authorization (permissions) for user types  
  * "Forgot my password" and friends
  * UI's for administration of users
  * Social logins. "Login via Instagram/Facebook". Good luck with OAuth.
  * Importing user's from an older system
  * ... I can go on and on ...
* All of those in a performant way, (reads "cached").

### What you can do:

#### 1) Do all those yourself: costs months, even up to 1 man-year.

* LOL no.

#### 2) Use one of your popular frameworks of your ecosystem. 

* Ready made user models and most of the functionality above.
+ Weeks to configure.
* Exactly why RoR, Django, Node/Express... saw explosive growth in late 2000's - early 2010's.
- Still not fast enough for this day and age.

#### 3) Use a hosted solution (Firebase/Parse/Auth0/Okta/AWS Cognito)

+ Cost hours/days (if your language is supported)
+ Younger generation's favorite AFAICS.
- Expensive after a threshold
- Platform lock-in to death. once you're in you're in.
- All closed source; no way to self host.
- Not much room for customization.

* Huge market; A few months ago Okta bought Auth0 for 6.5 billion usd.
* Firebase still haven't been abondoned by Google.

#### 4) aaaaaaand: HazelBase?

* Hazelcast Platform already provides most of the moving/crucial parts of a typical Backend app:
  * caching
  * it's a message broker
  * great IPC
  * clients for popular languages.
  * all sorts of integrations (S3, other databases, etc..)
  * all this in a simple to deploy package (nothing beats "java -jar" (well, except a Go binary))) and performant. 

Sitting on top all that; why don't we use it:  
 
1) Slap a webserver in front of Hazelcast Platform. 
2) Implement func. above; 
3) Let the developer use his preferred language/framework 
  *  communicate with Hazelcast via the clients or HTTP.
4) ... call this HazelBase? 
5) profit?

* This IMO is the killer use case for Hazelcast Platform.
* It could help a lot for brand awareness. 
  * (Sales team would appreciate that a lot; RedisLabs sales team must have a much easier life.)
  * Especially if it reaches to the younger generation. (xxx emphasis on that later)
* Hosted offering under Hazelcast Cloud umbrella.

# Emphasis on younger generation.

xxx

# xxxxxxxxxxxxxxxxx

# Intended audience

* Serial freelancers/small teams who copy/paste from their old Django/Rails/Node projects to hit the ground running on their new projects.
* Developers who want to get rid of depending on Firebase, Parse, Auth0, AWS Cognito, Okta etc... 
* Younger generation who want to spend as little time as possible on backend work.

# Technical Details

* The core will be a Java/Clojure web server. 
* Hazelcast will provide the caching and task execution and message queue layer. 
* Persistence layer will be Postresql or SQLite.

