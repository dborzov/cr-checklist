# Code Philosophy

At Kinetic we believe in investing into writing resilient and maintainable software.
We believe in design decisions that pay off in the long term even if they take more resources upfront.

We know that no rigid style guide or formal process by itself will address this. High quality software comes from the awareness arising from discussion and deep thinking on what works and what does not.

With that, take what follows as a conservation starter, not the ultimate set of unchangeable rules.

# Code Review Checklist
Code Review is the key institution we have to assure the code quality.
Arguably, deep and thoughtful CRs are more important that writing good code per se.

Things I pay attention to when reviewing code contributions (PRs):

* See the original ticket/story and make sure you understand the purpose of the work done
* Understand the state of the original parts of the code affected
* Check if the functionality of the affected parts of code is well documented in [the company's and project's specification wiki](https://halogenmobile.atlassian.net/wiki/display/ALDOCONF). Sometimes the specification of the unaffected functionality can be missing too and it is a good idea to amend this on the first notice, that is, within the same PR
* Can a person with only superficial acquaintance with the project understand why the affected code parts are the way they are? If the code is not self-evident, it may warrant some clarification code comments. Here are some traits of excellent code comments
   - When it feels like a comment is needed, it might be a sign that this code should be refactored to be more readable. Things like better naming and self-describing unit tests may make a difference. In the situations where the choice is explicit code vs efficient code the right answer is usually the former. Remember that [premature optimization is the root of all evil](http://c2.com/cgi/wiki?PrematureOptimization).
   - If the comments clarify the overall behavior of the system  (the program's API) they probably belong to the specification document (like project wiki), not to the code itself
   - unless it is not absolutely evident what the function or a method does, it may warrant a docstring. A docstring clarifies the functionality and purpose, not the implementation. A simple example of usage is also usually helpful.  
   - Comments within the code blocks clarify the code implementation. They tend to be helpful when they answer the question why, not how.
   - Superfluous comments are evil: as the code they describe evolves it easy to overlook them and make them obsolete. That makes them misleading and harmful instead.

# A perfect Pull Request Checklist

* Put links for the relevant specification wiki pages in the PR description
* Add the semaphore badge to show the status of tests passing

# Good code practices

## Writing code for unit tests
