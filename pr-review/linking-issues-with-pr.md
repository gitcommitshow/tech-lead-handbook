It was year 2012, I was a junior developer back then. One day, my colleague watches me copying link to a GitHub issue and sharing it in a Pull Request (PR). He comes to me and tells me that I can simply write the issue no. and it will be automatically linked. I am blown away with this tiny feature because it solves a major pet peeve I have.

If we can go back in time to tell this guy that you don't even need to search and write the issue no. and your related issues will automatically get linked in PR, younger me would probably go uncontrollably mad with the the joy.

I share this story to highlight the point where we are in terms of tech development. Now, it is not a necessity to link issues in a PR manually, an AI code review bot does a better job than us humans in finding the relevant issues and linking those with the PR. But it is definitely relevant for us humans to effectively leverage this tiny concept of "linking with PR" to make our code quality and engineering process better.

> We might do a good job in linking just the one issue for which we worked on that PR but AI tools can also find all those issues this PR impacts. Seemingly tiny but impactful feature.

In this chapter, we'll explore the reasons why one must link related issues to PRs. We'll highlight the common challenges developers encounter in doing so. And then we'll also talk about how can we leverage some tools to automate and improve this task of linking issues with PR.


> Example of linking related issues and assessing PR against the linked issues for [okp4/ontology/pull/220](https://github.com/okp4/ontology/pull/220) (these issues were linked automatically by [CodeRabbit](https://coderabbit.ai) PR review bot).


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f0y805uggvver0f0ed2f.jpg)

Let’s deep dive and understand this topic thoroughly.

## Linking related issues to PR

For developers and PR reviewers, there are two fundamental questions to consider for every PR:

1. What is the key issue this PR is tackling?
2. What are the broader implications of this PR on other existing issues?

And these questions are answered by identifying and connecting related issues to the PR. So this is apparent for many of us developers but let's understand the context in depth what does issue linking helps with.

### Why do we need to link the related issues for a PR?

Finding related issues for a Pull Request (PR) is an essential practice with significant importance for several reasons:

* **Prevents redundant work:** When issues are not linked to PRs, developers miss to close them, it can lead to issues not getting closed even after it has been fixed. Another developer spends time researching and developing only to realize later that it was already fixed by another issue. Another common problem is often duplicate issues get logged due to a disconnect. Linking issues to PRs prevents them from remaining open after resolution, averting duplicate efforts and confusion caused by other developers unknowingly working on these fixed issues. It streamlines the development process.
* **Better PR reviews:** When reviewers are aware of related issues, they can provide more informed and comprehensive feedback. This helps in identifying potential oversights or conflicts that might arise due to the new changes.
* **Better issue tracking and documentation:** When PRs are linked to issues, it creates a clearer historical record of why changes were made, which is valuable for future reference and new team members. If there are non technical folks on the team, they also get a good sense on what issues are now solved thanks to this PR.
* **Fosters collaboration:** When an issue is linked to PR team members can see the context and history of a problem, which helps with better understanding and more efficient problem-solving.
* **Improved code quality:** Understanding the wider implications of PR changes ensures that the code not only fixes a specific problem but also aligns with related issues.


### What makes it hard for developers to link related issues in PR

Let's be honest, finding and linking these issues is neither  a developer's favorite pastime nor it is as easy as it sounds. Let’s explore the challenges developers face in linking related issues:


* **Oversight:** Many times, developers are not aware of larger impacts to the code base. Which leads them to miss linking all the issues the PR is addressing. This is more common where the project and the codebase is not small enough or requires a significant amount of collaboration with others.
* **Lack of adherence to standard practices:** Inconsistencies in how issues are reported, described, or tagged can make it difficult to find related issues. Lack of standard practices in issue tracking can lead to inefficiencies.
* **Searching in a large project takes time:** For large projects with extensive issue histories, manually searching and identifying related issues can be a daunting and time-consuming task.
* **Difficulty in identifying relationships:** Understanding the interdependencies between different parts of a complex codebase can be challenging.  This complexity might cause developers to overlook related issues.
* **Information overload:** In large projects, the sheer volume of issues can be overwhelming, making it difficult to sift through and identify the most relevant ones.

### Solution: CodeRabbit (a PR review bot) automatically finds those issues using AI

CodeRabbit, an AI-powered PR review bot, simplifies this task by analyzing GitHub issues, performing the similarity search and linking the most relevant ones to your PR. See it in action:

[okp4/ontology/pull/220](https://github.com/okp4/ontology/pull/220)



![demo screenshot of issue linking with PR for ontology repo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f0y805uggvver0f0ed2f.jpg)


[ethereum-optimism/docs/pull/261](https://github.com/ethereum-optimism/docs/pull/261)




![demo screenshot of issue linking with PR for ethereum-optimism docs repo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0j4rdge1ilb4imez6ecs.jpg)


[usatie/pong/pull/111](https://github.com/usatie/pong/pull/111)



![demo screenshot of issue linking with PR for pong repo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w9lm4ao3v78y97ycjn1m.jpg)


## How to automate issue linking with PR

As of Dec 2023, CodeRabbit is the only practical solution I see to do this job. To set it up, just install the [CodeRabbit PR review app](https://coderabbit.ai/) in your GitHub repository. That's it. If you're curious to understand how does this app work behind the scenes, [check out this CodeRabbit deep dive blog](https://coderabbit.ai/blog/coderabbit-deep-dive).


## Conclusion

It is an essential task for PR authors and reviewers to identify issues related to the PR. We discussed how this simple-looking task could be challenging due to many reasons including oversight and project complexity. AI-powered PR review bots solve these challenges by automatically linking issues in the PR. As a tech lead, we should think about leveraging these tools and educate our team about the importance of this concept issue linking to improve our product and code quality.
