# Artemis_Financial
CS-305 Final Assignment

**Briefly summarize your client, Artemis Financial, and their software requirements. Who was the client? What issue did they want you to address?**

Artemis Financial aims to modernize its web application. The goal put forth is to use the most current and effective software security in order to protect their client's data and financial information. A few key improvements were updating them to use HTTPS, utilizing SHA-256 for creating checksums for verifying data being transferred, and lastly implementing a dependency vulnerability scan into their Maven lifecycle. 

**What did you do very well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?**

After seeing the initial code with 76 vulnerabilities and the need for current software I upgrades most of their base plugins to recent versions and implemented Spring Boot Security. This reduced the attack vector from 76 down to 4. A number of the flagged vulnerabilities were false positives as they affected earlier versions of the dependencies. Other measures included adding some more static analysis plugins such as PMD and Spotbugs. The code was analyzed in the IDE via Sonarlint. 
Coding securely and maintaining that mindset alleviates potential breaches that compromise data. Staying up to date and working toward a proactive mindset with security reduces being caught by surprise and constantly being in a reactive stance. Thus reducing burnout, stress, and other negative outcomes from a constant uphill battle. 


**What part of the vulnerability assessment was challenging or helpful to you?**

In terms of helpfulness, it put me down a rabbit hole looking into various static and dynamic code analyzers along with the sheer number of tests that can be applied to aid in producing better code throughout the build pipeline. It gave a good starting point for research and implementation for a larger project. 

**How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?**

By adding Springboot Security and configuring the application to utilize HTTPS for communication. Another configuration made was to block all non-HTTPS traffic via a redirect. Added a couple of extra static code analysis plugins during build time to catch any violations and flag the build failed if found. 
For vulnerability analysis, I’d likely add Sonarqube in conjunction with OWASP dependency check to keep a standing record. Identifying and mitigating plugins takes some research on the front end such as determining if they are false positives.  However, they could potentially be debunked by utilizing tests that target the specifically stated vulnerability and see if the implementation is secure. 

**How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?
What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?**

I verified post-refactoring whether I reduced or increased the attack vector in terms of vulnerability numbers. I did multiple checks of the dependency check report through the various stages of code change. Then I checked any existing vulnerabilities and saw if there were ways to utilize a secure version and overrode those dependencies with secure versions. 
This assignment was more of a view into my past when I spent a lot of time with Java builds utilizing Maven. I implemented a lot of things that I had used previously to create gates to ensure better coding from the developers checking in code. If I were to dig deeper into this I would likely create a parent pom that would enforce certain rules for all builds as well as exclude known vulnerable dependencies so they couldn’t accidentally be put in place. 


**Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?**

In terms of a technical portfolio, I would actually build a more complex web application and set up a way to automate all the infrastructure to aid in building and testing. Examples of this are a Jenkins build system, Sonarqube server, testing platforms, etc. 

