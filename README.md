# Zoo Authentication System

by **Edwin Richards** 

I have spent the past two and a half years in the Computer Science Bachelor's program at Southern New Hampshire University and it has been a great experience so far! 

After graduating high school, I still wasn't sure exactly what I wanted to do for my career. My father had been a police officer for many years so I was contemplating going in that direction for a career. But due to age restrictions on the job, I had to wait a while before I could try that avenue. I knew that college was pretty much a requirement because of the limited number of well paying jobs for those without a college education. So, I began taking general education courses at a local community college a year after high school. I did this off and on for a while and doing whatever job I could at the time.

After a little while, I decided to look through the different programs offerec at my community college. I stumbled across the Associate's Degree for a Computer Programmer/Analyst. It had a certain alure and I knew that programmers often made pretty good money. And even better, I had always enjoyed using and learning about computers! So, I enrolled in the degree program and took the first core course, Introduction to Logic. I started the class and I couldn't put the text book down! Everything just made so much sense! Apparently, I was a logical thinker. So, I moved on to the next course in which we did a lot more coding and I had a blast! The frustration experienced while writing the code and encountering cryptic error messages and compiler warnings was greatly outweighted by the satisfaction experienced once the program actually did what was intended. I was hooked and I knew I wanted to be a software developer.

Ultimately, I finished my associate's degree at the community college and then started putting out my resume and submitting applications for every "Entry Level Developer" position I could find. Even ones in other cities. But nothing ever panned out.. Everyone wanted a "Bachelor's Degree" or "Experience". I was a little disheartened, but I started looking at my options. I needed to find a university that offered a 100% online BS in CS because I had a family and full time job. Finally, I saw an advertisement for SNHU and decided to look at their programs. Bingo! Just what I was looking for! I was able to transfer many of my credits from my Associate's Degree and I enrolled at SNHU and haven't looked back since. And as luck would have it, I was able to snag a job as an entry level computer programmer only six months after starting courses at SNHU and I have never been happier!

I have really enjoyed the fast-paced courses and the knowledge I have gained being here. Additionally, I was able to secure a position as a peer tutor in the IT/CS category and I have been able to help so many other students to better understand code and develop a love for the world of programming! I am looking forward to finally earning my degree, but I will also kinda miss the whole experience, too!

-----

Working through the different courses has helped me to showcase my strengths in software development. In particular, in IT-145 (Foundation in Application Development), the course on which the remainder of this project is based, I went above and beyond to write the final application as a user interface application when all that was required was a console application. The reason I chose the UI app was to challenge myself a little. I have written so many console applications and I wanted to try a UI app in a new language (Java) since I was already familiar with UI apps in C#.

Another course in which I was able to showcase my strength in coding was CS-340 (Advanced Programming Concepts). In this course, we had to write a RESTful web API and incorporate a database backend using MongoDB. This was a challenge for me because I had only ever worked in relational database management systems and NoSQL was a whole new world for me. But the structure of MongoDB syntax was not overly difficult to understand and I was already familiar with the Python language. I expanded a lot on the example code provided for writing the API to include reading and writing HTTP request and response headers and I incorporated a lot of error handling and portability. Overall, I was very pleased with the final result and I had a lot of fun getting everything to work!

I also found CS-310 (Collaboration and Team Projects) to be extremely helpful. I had used source control software before at work, but we weren't using git at the time. CS-310 was all about how to use git with multiple developers (the other students in the course) on the same project. I learned so much about how to use git. Recently, our company switched to git for our source control software and now I am the resident expert!

Going through the different required courses for the CS program at SNHU has shaped my professional goals as well. I have learned specifically that I don't want to be in a management role and I definitely don't want to be a database administrator! I had to take a project management course and, while the content was useful in understanding modern Scrum project management, I did not find as much enjoyment in that course as others. Additionally, I took a DBA course in which we had to act as a database administrator working to scale a company's current database structure. That is another course that was interesting, but not for me. I developed a new found respect for DBAs but I do not want to deal with that stuff on a daily basis. I much prefer to just be a software developer who writes and fixes code all day. 

This is an authentication/authorization system rewritten from IT-145 (Foundation in Application Development). The original requirements were: 
* Write an authentication system that gives a user three attempts to log in. 
* After three failed attempts, the program should display a warning and then close.
* Upon successful authentication, the program should display only the details allowed for the role assigned to the logged in user.
* The user should have to option to log out of the system to allow a new user to log in.

### Demo and Code Review
<iframe width="640" height="360" src="https://www.youtube.com/embed/ZPmXtRK2rYw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

This Cap Stone project is supposed to address and enhance three main concepts from the original program:
* Software Design and Engineering
* Algorithms and Data Structures
* Databases

### Software Design and Engineering
  The artifact I selected is a Zoo Authentication program that I originally wrote for the course IT-145 (Foundation in Application Development). I submitted the final project for that course in August of 2017. For the final project in that course, we were given the choice between two projects. One option was an authentication system, the other was a monitoring system. I chose the prompt for the authentication system simply because I felt it was most practical. In today’s day and age, security is a imperative in virtually any application. Being able to protect data behind a login screen and then only display the amount of information allowed for the current user is an invaluable piece of knowledge for a software developer.

  When I took the course, I was already familiar with making event-driven, user interface applications. Even though the rubric specified a console app was all that was necessary, I wanted to challenge myself a little bit so I made a UI app with the Java Swing library. This helped to showcase my ability in developing real-world applications.

  For the category of Software Design and Engineering, I decided to convert the application from the original Java Swing UI into a Windows Presentation Foundation (WPF) app using C#.Net and incorporate an MVVM design pattern. 

  I chose WPF and MVVM because I am very familiar with the technology and concepts from work. But during the conversion into WPF, I learned how to make use of a content switcher control to change which view is being displayed within the same window. This is a different behavior than in my original application because in that one, I opened a new window rather than just changing the content. But the content switcher works wonderfully.

### Algorithms and Data Structures
  Something I learned about when I was originally writing the application in IT-145 was how passwords should be stored for authentication. Prior to the course, I knew passwords shouldn’t be stored in plain text because, well, it’s highly readable to anyone who can open the file. But I wasn’t sure what the standard encryption was. Turns out, most applications utilize the Message Digest 5 (MD5) hashing algorithm to hash passwords and then they store the hash for validation. The MD5 hash is a 16 byte (128-bit) one-way hash. Using a one-way hash is important because if anyone is able to acquire the hashed value, then they can not reverse the algorithm to determine the original password. The problem these days is that the MD5 hashing algorithm is so widely used that attackers have dictionaries of the hashes of the most common passwords. So, if they are able to get access to a list of hashes, they are then able to lookup the plain text that creates that hash. 

  For my enhancement, I chose to modify the hashing algorithm used by my application. Instead of the more common MD5, I updated it to use the SHA256 which is a 32 byte (256-bit) one-way hashing algorithm. This is a little more secure because of the increase in the size of the returned hash. 

  Simply changing the code, however, is not sufficient for the enhancement because if the application generates a SHA256 and tries to compare it to the stored MD5 hash, it will never find a matching password. So, I had to also update the credentials file and change all the MD5 hashes to the equivalent SHA256 hash and then the authentication still worked.

### Databases
  While working in my current position as a software developer, I have become very familiar with using databases to store and manipulate data in the back end of an application. The third category in which we were supposed to enhance the original application is the use of databases. The original authentication system I wrote in IT-145 did not contain a database back end. Instead, the application validated user input using a text file containing the valid credentials. For this enhancement, I wanted to keep everything in a database to improve security and functionality. 

  I developed a database to do just that. I used Microsoft SQL Server because that is the RDBMS with which I am most familiar. I created a new database with two tables. One table contains the valid credentials including the username and the new SHA256 hashes for the passwords. Along with those values for each valid credential, I also keep track of the number of failed attempts as well as a bit to indicate if the account is locked or not. It’s also worth noting that I do not store the plain text value for the password anywhere in my database. 

  The second table I created contains the role data including the greeting and the description of the authorized tasks. Then in the credentials table, I link a credential to the appropriate role.

  Additionally, I developed a couple stored procedures to help operate on the tables that I created. There is a stored procedure that I use to authenticate a user. It takes a username and hash that will be supplied by the application and looks for a matching record that is not locked in the database. If a match is found, it returns the appropriate role information retrieved from the linked table. Otherwise, it returns a failed result. I also wrote a stored procedure that will unlock an account. This makes the application easier to work with for the purposes of education and testing. Instead of having to go into the database and manually adjust the data, I can call a procedure firectly from the application to do that for me.

  After developing the backend database, I needed to interface with the database from the application. To do that, I adjusted my validate action to reach out to the database instead of reading the file. I also added another action linked to a second button on the screen to execute the database procedure to unlock a user account. And finally, I added the database connection string into the configuration file for the application so that the app knows where to locate the database to use for validation. 

  I decided to do it this way because it makes for a more maintainable application. If the database connection changes at all, then I can just modify the configuration file and restart the application rather than changing code and having to recompile. When testing the functionality of the application, it works as expected. None of the functionality from before is lost and now, the database will keep track of which accounts are locked. So, if user A exceeds 3 failed attempts, the application doesn’t close and user B can still attempt to log in to the system.
