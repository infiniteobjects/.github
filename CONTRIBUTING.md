# IO Developer Manifesto

## Pivotal Workflow

- Make stories as small and specific as possible
- Add detailed descriptions, acceptance criteria, tags, and estimates (even if rough)
- Set up related stories as blockers where appropriate

### Story States
The following table explains how we interpret each of the states for a Pivotal story. Note the difference between Finished & Delivered

| States    | Description                                                                                 |
|-----------|---------------------------------------------------------------------------------------------|
| Unstarted | When the story is created                                                                   |
| Started   | When you pick up a story                                                                    |
| Finished  | When the code for a story is considered complete by the author(s), and a PR has been opened |
| Delivered | When the story is deployed, visible, or otherwise testable                                  |
| Accepted  | When the story has passed all tests, reviews, QA                                            |
| Rejected  | When the story has failed one of the above                                                  |

## Git Workflow

- We use [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/)
- Never push directly to master/main or develop branches
- Only submit our changes via opening Pull Requests
- Post all new Pull Requests to #pull-requests
- Strive to make a single Pull Requests encompass 1 piece of functionality.
- Use GitHub for tracking code reviews
- Use Pivotal Tracker for tracking all other reviews (design, testing/QA, etc.)
- Pull Requests by a single developer needs 2 approvals
- Pull Requests by a pair needs 1 approval
- Authors cannot approve their own Pull Requests
- For a very small PR the developer has the choice to only have 1 approval, **please be mindful**
- Delete branches after they have been approved and merged

### Branch naming

- Add `[pivotal-id]` to the end of the branch name, removing the # sign from the story number
  - Pivotal Tracker looks for this ID to link the branch to the story 
- release-id's are calculated [2 digit year].[2 digit month].[version]
  - (e.g) 22.04.1 (1st release of april 2022)

| Types   | Branch Name                           |
| ------- | ------------------------------------- |
| bug     | `bug/[branch-name]-[pivotal-id]`      |
| chore   | `chore/[branch-name]-[pivotal-id]`    |
| feature | `feature/[branch-name]-[pivotal-id]`  |
| hotfix  | `hotfix/[branch-name]-[pivotal-id]`   |
| release | `release/[release-id]`                |
| epic    | `epic/[epic-name]`                    |

### Commits

Commits should conform to the [Conventional Commits spec](https://www.conventionalcommits.org/en/v1.0.0/). See the spec for a full list of types and these examples:
  - `feat:` additional functionality was added to the code
  - `fix:` logic was fixed/changed/updated (bug, etc)
  - `refactor:` code was moved around but logic was not changed
  - `test:` test (unit/integration/etc) or results of a test being conducted were added
  - `chore:` ran repo command (rush/git/etc)

The commit scope is optional but encouraged.  It should be the package name where applicable.

```bash
> git commit -m "feat(api-eth-tokens): ..."
```

In the example above it is very clear that this commit is a feature being added to the `api-eth-tokens` package.

Some other things to note about your commit messages:
- Have descriptive, meaningful commit messages
- Spell check our commits so that they look good in our change log
- Squash commits to clean log if necessary
- Start our commits with a present tense verb and Sentence case
  - (e.g) feat: Adds product description component
- Do not check in anything that outputs any warnings in the console or terminal output

## Pull Requests

### PR Pyramid
![The Code Review Pyramid](https://user-images.githubusercontent.com/49962954/157915476-948445aa-6a6c-4c1a-af52-08b87ef6a3a7.png)

### PR Etiquette
- PR titles will be short, readable and descriptive
- PRs will be reviewed by the team every morning (at least once a day) to ensure no features are blocked because no one has reviewed them
- Things that can block PRs
	- Does not meet product spec
	- Does not meet architecture spec
	- No 1 character named variables
	- Dangerous code security wise
	- Inefficient
	- Lack of testing
- Feedback that should be given
	- Commented out code that does not say why we have not deleted it the commented out code
	- Feedback on the format of the code including readability issues
- If there is a change that should not block the progress of the PR but should be revisited it can be placed as a chore in the backlog

## TypeScript

- Treat warnings as if they were errors
- Try not to use `any`
  - Use `unknown` where possible
- Use [TSDoc](https://tsdoc.org/) styling to document all functions

## Styling

- Use kebab-case for any files
- Use kebab-case for any Collection names
- Use plural naming for any Collection names (users)
- Use camelCase for any field names in the database
- Use camelCase primarily in javascript/typescript
- Nest files in folders and name them according to their scope
- Take the time to refactor anything we see that breaks with the rules of our manifesto 
as long as it is within a reasonable scope for the PR

## Folder Structure and Variable naming

- Nest files in a folder that should be grouped

## Refactoring

- We **refactor as we go**. 
- If there is a refactor that we can do then and there to help the team we should strive to do it within reasonable scope  

## React

- Avoid API calls and other business logic in components
- Use the Presenter Model if possible
  - Presenter model must use a .scss/.css file
  - Should not be doing logic
- Use functional components with React Hooks

## CSS

- Use [BEM](http://getbem.com/) for our CSS naming convention
- CSS names should be tied to the component name
- CSS should live alongside the component and only style that component

## Testing

- Create UI tests (cypress/playwright) for any critical path features
- Create regression tests for bugs
- Integration tests should live in a test folder outside of src directory
- All unit tests should live alongside the file they are testing
- We use [crossbrowsertesting](https://crossbrowsertesting.com/) to test across browsers
- When we encounter or make edits to code that does not have test coverage we will go the extra mile and create tests even for code we didn't write ourselves.

### Testing Best Practices

- Make generic tests that will not break during refactors or Data Changes
- Integration tests should **NOT** use specific values from a database because values will change over time
- Use regex or something generic when testing for equality
- When accessing DOM elements in test use an id that is prefixed with `#test-` that way anybody updating the
  component will know not to change that id name

## Bugs
- Create a separate Story and PR for all bugs
- User-facing bugs require alignment with Product
- Dev-only bugs can be handled by the dev team
- Make sure to use the IO 'Bug Report' template (see photo below)
<img width="264" alt="bug-template" src="https://user-images.githubusercontent.com/18608739/157771488-4e29609c-2df7-4d40-a30d-d0467e621669.png">


## Accessibility 
- Associate a label with every form control
- Include alternative text for images
- Identify page language and language changes
- Use mark-up to convey meaning and structure
- Help users avoid and correct mistakes
- Reflect the reading order in the code order
- Write code that adapts to the user’s technology
- Provide meaning for non-standard interactive elements using `aria`
- Ensure that all interactive elements are keyboard accessible
- Avoid CAPTCHA where possible
- Use color blind accessible colors


## Dependencies
- Use `npm ci` instead of `npm i` when installing/updating a branch, unless there is a specific reason to do so
- Update dependencies in a separate `chore` branch dedicated to only updating and testing dependencies

### Repository Owners
- Each developer will be assigned a project which to maintain dependency health
- Each developer should PR a branch with updated and tested dependencies, or noted considerations in not updating.
- Have these PRs finished by 🎉 Launch Party 🚀 which, at time of writing, is scheduled for Tuesdays
- We will strive not have any dependabot PRs longer than a week

| Developer   | Repository                       |
|-------------|----------------------------------|
| Marc        | Print Your Own     		 |
| Jorge       | Stack 				 |
| Nico        | UI 				 |
| Paul        | Shopify Theme 			 |

### Choosing Dependencies
- Choose dependencies that are stable, active, and well maintained
- To qualify as active/ well maintained it should meet these criteria:
  - The last commit was within one year to date
  - How many contributors, is there a company backing the project, or a whole community
  - Don't pull in branches contributed by only one developer
  - How many open PRs? and is anybody reviewing them
- Is it stable? - How many open issues and how long do issues take before they are fixed
- How many downloads, we want to find packages that have at least a couple thousand downloads
- Follows semantic versioning MAJOR.MINOR.PATCH (e.g. 2.5.1)
- License permits intended use
- It has quality documentation
- Avoid specific software version dependencies
- Our `package.json` file should use the `~` will update the package to the latest patch version.
  - (e.g. `packageName: ~1.0.2`)
