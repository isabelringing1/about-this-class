# Taking quizzes

Most of the class meetings include pre-class reading and a
quiz that covers that reading. You will take those quizzes
using the [class API](https://www.cpsc213.io/openapi/).
(We are working on adding quiz-taking to the class website
and we'll have it done soon. In the meantime, we apologize
for your suffering and hope that, at the minimum, it is 
character building.)

To use the API, there are a few steps:

1. Get your [JSON Web Token](https://jwt.io/introduction/) for the class API. This identifies you
   and allows you interact with the API (though, there are some things you can do anonymously).
2. Find the next class session.
3. Find the quiz corresponding to that class.
4. Create a quiz submission.
5. Show the quiz questions.
6. Show the choices for each question (the questions are multiple choice).
7. Submit your choice for each question.

You can do this using any tools you like. For example, it is easy to write a shell,
 JavaScript, Ruby, or Python script for interacting with the class API. You can also
 use programs like Postman, which give you a GUI for interacting with APIs. Here,
 I am going to show you to how do this all "by hand" on the command line using CURL,
 a common command line HTTP client you will find available on most operating systems.

 ## Get your JWT

 You should log into the [class website](https://www.cpsc213.io/) and then visit
 your [dashboard](https://www.cpsc213.io/#/dashboard), which shows a few pieces of
 information, including a freshly generated JWT. (The JWT will expire in two days
 or so.) You want to copy this value. If you're on a
 [Posix compliant](https://stackoverflow.com/questions/1780599/i-never-really-understood-what-is-posix)
 shell, like Bash, which is likely, you can do this as follows:

 ```
 export JWT=eyJhbGciOiJIUzI1NiIsInR5c...
 ```

 Above, the "..." indicates that I elided the rest of that value. 

 2. Find the next class session.

 ```
 curl 'https://www.cpsc213.io/rest/meetings'
 ```

 That will dump a lot of information, and you don't need it all. You're
 probably only interested in the *next* few classes. So, add a query as 
 follows


 ```
 curl 'https://www.cpsc213.io/rest/meetings&begins_at=gt.2018-01-17&limit=3'
 ```

 This says, "get the first three classes with `begins_at` greater than 2018-01-17".
 Now, there is still too  much information, so let's get only the `meeting_id`,
 `begins_at`, `title`, and `slug`. (The "slug" is the URL-friendly identifier.)
 The query format is described in the 
 PostgREST documentation](https://postgrest.com/en/latest/api.html).

 ```
 curl 'https://www.cpsc213.io/rest/meetings?order=begins_at&limit=3&begins_at=gt.2018-01-17&select=id,title,slug,begins_at'
 ```

The output is in [JSON](https://www.json.org/) format, which is a common format
for APIs. If you want to make it look pretty, you can pipe it through a program
that will format the JSON. 