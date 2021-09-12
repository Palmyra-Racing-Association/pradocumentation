## Code repos
We have a few code repos that are storing a few different things. They were all created at different times as side projects.  These are the things I refer to as "perpetually 80-90%" complete.

[clubmanager](https://github.com/adelimon/clubmanager) - this is the main webapp repo. Spring Boot and angular app.  Java 1.8 and angular 1.4.  This powers (https://apps.palmyramx.com), as well as our test environment.  Mostly in bugfix mode, but generally stable and works well minus a few annoying usablity things.  This runs on an EC2 instance.

[prarenewalui](https://github.com/Palmyra-Racing-Association/prarenewalui) - a basic React form for processing renewals.   React and JavaScript.  This is accessed at (https://renew.palmyramx.com) with a user token, ie: (https://renew.palmyramx.com/?token=47-14450-2011). The intent is to provide one click renewal without login.  Functional, gets the job done, but ugly.  Static website in an S3 bucket.

[praapplication](https://github.com/Palmyra-Racing-Association/praapplication) - a basic React form for capturing new member applications.   React and JavaScript.  This only gets touched when needed which is not very often. Static website in an S3 bucket.

[prarenewalapi](https://github.com/adelimon/prarenewalapi) - a REST api, in Express, that supports the React UIs as well as Amazon Connect.   It’s essentially the “other” api fronting the MySQL instance.  JavaScript. Runs as an AWS Lambda fronted by API gateway.

[praconnect](https://github.com/Palmyra-Racing-Association/praconnect) - this is a CDK and AWS Lambda project supporting infrastructure used mostly by our Amazon Connect IVR. Code to support text messaging, weekly points emails, and billing are in this repo too.  Typescript, JavaScript, CDK, and Terraform.  In the world of "Alan's latest crazy ideas", this is the latest and greatest and I'm actively contributing to it.  

[pra-points-aggregator](https://github.com/adelimon/pra-points-aggregator) - Used to aggregate data from MySQL into historical reporting.  Used for current year member points and will be used for billing the 2021 season.   It is used to figure out things that are too much work to figure out in SQL, but easy to do in Javascript.  Javascript, accessed as an NPM library.  Closely tied to praconnect, and a consumer of prarenewalui.