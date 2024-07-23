# Hello 👋 My name is Utku
Welcome to my website. I'm a full-stack web developer interested in all things web; particularly React, TypeScript, offline-first (local-first) web apps and open source. I've built this page to express myself and host my future blog. It is a statically generated website (SSG) based on a Markdown file.


## Current work
I'm currently in charge of all technical aspects of Flora, a sustainable lifestyle platform. Below are some of the things I've accomplished here.


### Jumpstart the online marketplace
Based on a popular Shopify theme, we've launched our online marketplace. Although Shopify themes do not have React or TypeScript, they have HTML, CSS, JavaScript and Liquid, a popular and mature template language.

Working with these technologies have solidified my web fundamentals, as I had to gain a better understanding of them in order to implement certain requirements. Specifically, I gained a better understanding of the JavaScript event system, such as event propagation (capturing and bubbling) and modern CSS by utilizing CSS grid, flexbox and media queries.

Additionally, we are currently developing a custom, in-house Shopify app for our marketplace. Our motivations are overcoming the limitations of the existing apps and establishing interdependencies between certain functionalities of the apps that we use.

Shopify apps use Remix, a React framework based on React Router. Hence, while developing our custom Shopify app, I'm working with React, React Router, TypeScript and Tailwind CSS.


### Establish a business intelligence pipeline using Amazon APIs, BigQuery and Google Sheets
In addition to our online marketplace, we are also selling our products on other online marketplaces, the most prominent of them being Amazon. Regular insights are paramount for performance and efficiency. Hence, we established a system where we fetch business data from Amazon APIs regularly and feed them into the SQL tables and views that we've formed on BigQuery. This enables the members of the business team to gain insights by accessing this data using the BigQuery connector on Google Sheets.

I've established this pipeline by doing research for configuring the Amazon APIs, which was a bit ceremonial and then implementing the ETL code in TypeScript, using the [TypeScript template that I've created](https://github.com/ugultopu/typescript-eslint-prettier). This code acts as the glue that fetches data from the APIs, transforms it and loads it to the SQL tables on BigQuery, which I have designed and implemented.


## Open source
I'm a proponent of open source, both as a user of many open source projects and as a contributor to some of them. Here are some of my open source contributions.


### Projects that I've created
I have designed and developed a few open source projects from scratch. All of these born of a need of overcoming a problem that I was facing when working on a project.


#### Babel plugin that enables writing properly aligned multiline template literals
I wrote a Babel plugin named [Dedent Template Literals](https://github.com/ugultopu/babel-plugin-dedent-template-literals). This Babel plugin enables you to indent your multiline template literals so that they will look good on the source code, while not including the whitespace that's used for indenting. Further information is available in the documentation of the project.


#### Git command that enables rapidly experimenting with the repository (mention git-snapshot)
I wrote a Git command named [git-temp](). My motivation to write this command was to take a snapshot of the current state of the repository, without losing my current changes.

To give a concrete example, I occasionally encounter a TypeScript error in one state of the codebase and after making some changes, the error is gone. I don't always understand the underlying cause of the TypeScript error and hence, don't understand why it was occurring before and why it's fixed after. In order to investigate this behavior later on (when I have more time), I need a way to save the current state of the repository somewhere.

This command helps me with that. Running the command saves the state of the Git index and the working directory in different commits, creates a new branch and notes down the name of the branch that I was at. Later, after I'm done with experimenting, I can quickly get back to the state of the repository by simply running a command. Further information is available in the documentation of the project.


#### TypeScript project template
[This is a GitHub template](https://github.com/ugultopu/typescript-eslint-prettier) that lets you quickly set up a TypeScript project configured with ESLint and Prettier. It is ideal for Node.js (backend) projects. Further information is available in the documentation of the project.


### Functionality improvements on open source projects
In addition to creating open source projects from scratch, I have contributed to existing open source projects. Similarly, these were born of a need of overcoming a problem that I was facing when using a project.


#### Enable Visual Studio Code users to configure Git to better detect file renames
Diff command of Git has an option named `--find-renames`. This option enables the user to configure Git's file rename detection by configuring the amount of file similarity that Git should accept as a rename.

This feature was not available on Visual Studio Code. I have created both an [issue](https://github.com/microsoft/vscode/issues/178265) on GitHub, as well as a [pull request](https://github.com/microsoft/vscode/pull/178266) that implements this. My proposal has made its way into Visual Studio Code and I'm credited on the [release notes of v1.79](https://code.visualstudio.com/updates/v1_79#_thank-you).


#### Improve command selection functionality on Git's documentation website
Git's documentation website, `git-scm.com`, has a feature that lets a user select and copy the `git --version` command, which will enable the user to check their Git version.

![Selectable `git --version` command on Git's website](git-website-selectable-git-version-command.png)

Previously, this functionality was implemented as a regular HTML input element on the website. Furthermore, the contents of this element were editable. This wasn't a ideal solution, so I wanted to fix this. To do so, I have created a series of pull requests.


##### Make the HTML element for `git --version` readonly
[This pull request](https://github.com/git/git-scm.com/pull/1569) simply adds a `readonly` HTML attribute to the `input` HTML element that represents the Git command component shown on the screenshot above. It prevents the user from editing it, but it certainly is still the semantically incorrect HTML element to use.


##### Use a semantically proper HTML element to represent the `git --version` command
[This pull request](https://github.com/git/git-scm.com/pull/1575) converts the relevant HTML element from `input` to a `code` element with an embedded `span` element.


##### Use CSS `content` property to represent the shell prompt
[This pull request](https://github.com/git/git-scm.com/pull/1578) is an improvement of the previous one. Previously, clicking on the Git command was selecting the shell prompt character as well. This is undesirable since the purpose of the selection is to provide a user a quick way to copy and paste the command on their terminal in order to figure out their Git version. If the selection includes the shell prompt, they will need to manually alter the selection to exclude the shell prompt character (dollar sign) before they can paste the command to their terminal and run it.

This commit refactors the HTML elements so that the shell prompt is not included in the HTML content, but represented as an anonymous replaced element using CSS `content` property. Hence, it becomes non-selectable.


#### Fix an issue with URL fragment identifiers on Mozilla Developer Network's documentation
[This pull request](https://github.com/mdn/yari/pull/2385) fixes an issue on MDN where fragment identifiers are generated incorrectly. Prior to this fix, some fragment identifiers were broken on MDN.


### Documentation improvements on open source projects
Whenever I spot a mistake or room for improvement in the documentation of an open source projects that I use, I strive to improve them by making a contribution unless I'm time constrained. This contribution is sometimes in the form of a Git pull request, other times in the form of a filing a report ("issue" on GitHub). Some of the documentation and website improvements that I've done on open source projects are as follows.


#### Improve Git's documentation by refactoring some obsolete terms for "index"
The "index", which is the staging area that dictates the shape of the next commit in Git, historically had many different names. Some of these obsolete names were still present in Git's documentation. [This pull
request of mine](https://github.com/git/git/pull/943) has removed these obsolete terms from Git's documentation.


#### Document that `--date` argument of `git-commit` accepts approxidates
[This pull request](https://github.com/git/git/pull/969) improves Git's documentation by making it clear that `--date` argument of `git-commit` accepts approxidates. Approxidates are human-centric date formats, such as relative dates like "yesterday" or "last Friday at noon".


## Previous work


### Cosuno
In my previous role, I worked as a full-stack developer at Cosuno. Cosuno is a platform which brings subcontractors and general contractors together. This provides more work opportunities for subcontractors and provides the general contractors with a catalog of competent subcontractors. This leads to a more efficient construction marketplace.

As a full-stack developer I worked on improving the platform by implementing new functionalities and fixing existing bugs. I had the opportunity to work with technologies such as React, TypeScript, Node.js, ESLint, styled-components, Cypress, Formik, Docker, AWS, MySQL and Elasticsearch.

Further information can be obtained from [Christoph Werner](https://www.linkedin.com/in/christophwerner/), my manager at Cosuno.


### TOOLBX
Previously, I worked as a full-stack developer at TOOLBX. TOOLBX is a platform that improves the lives of its customers by freeing them from construction material supply runs. Customers simply place their order on TOOLBX, select their preferred delivery method and TOOLBX handles the delivery of construction materials.

At TOOLBX, I had the opportunity of wearing multiple hats. In the former half of my employment at TOOLBX, I worked as a full-stack developer. As a full-stack developer, I worked on improving the platform by implementing new functionalities and fixing existing bugs.

In the latter half of my employment at TOOLBX, I wore the hat of a developer experience engineer, focusing on fixing company-wide, infrastructural problems. This was a great opportunity because it allowed me to have a positive impact on the lives of my teammates, as well as providing me with an even deeper understanding of our codebase. In particular, two infrastructural projects were the most impactful.


#### Augmenting TypeORM types to provide type safety when fetching nested relations
TypeORM is a TypeScript based object-relational mapping library. We used TypeORM on TOOLBX. However, one problem that we were having was that TypeORM was not able to properly denote the return types when we requested used a nested relation.

I overcame this problem by customizing the type declarations of TypeORM, using advanced TypeScript techniques such as conditional types, mapped types and generic types.

The project was a huge success, fixing the type errors and hence, significantly reducing our run-time errors.


#### Migrating our codebase from Bitbucket to GitHub
We used to use Jira for ticket management. However, we later migrated to Asana. This removed the benefits of using Bitbucket. Partly for better developer experience, we decided to migrate to GitHub.

Moving the repositories themselves weren't a challenge. The challenge was to migrate the CI/CD pipelines to GitHub. GitHub Actions had a different syntax and own idiosyncrasies compared to Bitbucket Pipelines. Hence, the CI/CD pipelines needed to be carefully migrated and code changes needed to be made for the pipelines to work with GitHub Actions. I was tasked with this project and I reached this project to success. The result was a much better developer experience with quicker running CI/CD pipelines.


Further information can be obtained from [Kerry Zhu](https://www.linkedin.com/in/kerry-zhu-b044926b/), my manager at TOOLBX.
