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

You can do this using any tools you like. It is easy to write a