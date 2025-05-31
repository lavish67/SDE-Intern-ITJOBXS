# SDE-Intern-
( In the MySQL database, there is a user table that contains information like username, password, and email id.  These are going to store as a string in the database.

PHP is used to fetch html data & send it to the database. When the user fills in all the necessary information to register as a new user, PHP will send the html data to the database. )


A few months back, one major issue occurred on the itjobxs.com website,  which was making the website look vulgar & the database was reaching its limit quickly. 

The problem was many fake accounts were getting registered by bots & they were using itjobxs.com by posting about different websites (basically, they were doing advertisements about the websites like myntra, amazon, etc.). 

Solution:- 

Temporary Soln. :- One thing i have noticed is an email containing domains like gmail.com, hotmail.com, and yahoo.com needs phone no. to verify a new email id when created. So, i came up with the idea that for any user, if their email id does not contain gmail.com, hotmail.com, and yahoo.com,i will remove that user from the user table of the database by writing a simple delete query.  

(Users who registered with an email id other than those mentioned above are considered fake bots. It is because they were using other email IDs to register as a user.I have to understand that these email ids do not need phone no. to verify these bots. So, lakhs of such emails can be created & used by someone for advertisements. 

Actually, what we got to know,  all the fake bots were not using the emails of top domains to register as a user. That’s why we have removed the users not having emails from the top domain.)

But this is a temporary solution. , because you will have to run a delete query regularly at an interval to delete bots from the database.   

Permanent Soln. :- Since deleting bots from the user table of the database is a time-consuming process. So, this time i came up with an excellent solution. I told my seniors that during the new registration of a user,  if we put a check condition in PHP such that if they place an email id other than gmail.com, yahoo.com, & hotmail.com, then it will show an error & the user will not get registered at DesiQnA. 


By doing this, we do not have to run the delete query in the database regularly at an interval.  But still, there is an issue with this soln. as well. 

What about if a real person comes to register as a user on itjobxs.com, but their email id is other than those mentioned above domain name?

Due to the above condition, this user will also get considered a fake bot.

So, to remove this, my senior suggested finding the top 100 valid domain names from the internet similar to Gmail.com, etc. & putting them into the hashmap. This hashmap is in PHP. So, the condition has changed & now it is, during the registration of a new user, if their email id is not from the 100 valid domains then it will not present in the hashmap, it will show an error & user will not get registered on itjobxs.com. So, in reality, you have used data structure to resolve this issue.  
Final Soln. :-  
Integrate the Google recaptcha code into the html code.   

(Watch how to integrate Google recaptcha code)

My seniors had suggested integrating the Google recaptcha code into the index.html file. By this, you have made the website fully secure because bots can’t pass the recaptcha test. Hence, only genuine users will get registered. 

![image](https://github.com/user-attachments/assets/a3e14338-976f-4e9b-91ec-7b8f6f925756)
