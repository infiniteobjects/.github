# IO Developer Manifesto

## Story Size

- We will strive to make stories as small as possible.

## Git Workflow

- We use [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/).
- We will never push directly to master/main or develop branches
- We will only submit our changes via opening Pull Requests
- We will post all new Pull Requests to #io-pull-requests
- We will strive to make a single Pull Requests encompass 1 piece of functionality.
- Pull Requests by a single developer needs 2 approvals.
- Pull Requests by a pair needs 1 approval.
- Authors cannot approve their own Pull Requests.
- For a very small PR the developer has the choice to only have 1 approval, **please be mindful**
- We will delete branches after they have been approved and merged.

#### Branch naming

- We will add `#[pivotal-id]` to the end of the branch name
- release-id's are calculated [2 digit year].[2 digit month].[version]
  - (e.g) 22.04.1 (1st release of april 2022)

| Types   | Branch Name                           |
| ------- | ------------------------------------- |
| bug     | `bug/[branch-name]-#[pivotal-id]`     |
| chore   | `chore/[branch-name]-#[pivotal-id]`   |
| feature | `feature/[branch-name]-#[pivotal-id]` |
| hotfix  | `hotfix/[branch-name]-#[pivotal-id]`  |
| release | `release/[release-id]`                |

#### Commits

- We will have descriptive, meaningful commit messages
- We will spell check our commits so that they look good in our change log
- We will start our commits with a present tense verb
  - (e.g) Adds product description component
- We will not check in anything that outputs any warnings in the console or terminal output
- We will strive to follow [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)

## Pull Requests

- PRs will be reviewed by the team every morning
- **PR Titles**: will be short and descriptive

#### PR etiquette

- We will all look at open PRs at least once a day, to ensure no features are blocked because no one has reviewed them.
- Things that can block PRs
  - Does not meet product spec
  - Does not meet architecture spec
  - No 1 character named variables
  - Dangerous code security wise
  - Seriously inefficient
  - Serious lack of testing
- Feedback that should be given
  - Commented out code that does not say why we have not deleted it the commented out code
  - Feedback on the format of the code including readability issues
- If there is a change that should not block the progress of the PR but should be revisited it can be placed as a chore in the backlog.


## JavaScript / TypeScript

- We will use TypeScript as our base language
- We will treat warnings as if they were errors.
- We will strive to not use `any` when at all possible

#### Styling

- We will use snake_case for any routes
- We will use plural naming for any routes (/users)
- We will use kebab-case for any files
- We will use kebab-case for any Collection names
- We will use plural naming for any Collection names (users)
- We will use camelCase for any field names in the database
- We will use camelCase primarily in javascript/typescript
- We will nest files in folders and name them according to their scope
- We will take the time to refactor anything we see that breaks with the rules of our manifesto 
as long as it is within a reasonable scope for the PR

#### Folder Structure and Variable naming

- We will nest files in a folder that should be grouped
- We will refactor as we go

#### Refactoring

We **refactor as we go**. When we touch new files, if there is a refactor that we can do then and there to help the team we should strive to do it within reasonable scope. 

When we encounter a file, function, component without a test we will strive to write a test for it.

#### React

- We will avoid API calls and other business logic in components
- Strive to use the Presenter Model
  - Presenter model must use a .scss/.css file
  - should not be doing logic
- If a Component does not require state use a Functional Component

## CSS

- We use [BEM](http://getbem.com/) for our CSS naming convention
- CSS names should be tied to the component name.
- CSS should live alongside the component and only style that component.

## Testing

- We will strive to create UI tests (cypress/playwright) for any critical path features.
- We will strive to create regression tests for bugs
- Integration tests should live in a test folder outside of src directory
- All unit tests should live alongside the file they are testing
- We use [crossbrowsertesting](https://crossbrowsertesting.com/) to test accross browsers

**NOTE** When we encounter or make edits to code that does not have test coverage we will go the extra mile and create tests even for code we didn't write ourselves.

#### Testing Best Practices

We will strive to make generic tests that will not break during refactors or Data Changes

- Integration tests should **NOT** use specific values from a database because values will change over time
- Use regex or something generic when testing for equality
- When accessing DOM elements in test use an id that is prefixed with `#test-` that way anybody updating the
  component will know not to change that id name.

## Bugs

- We will create a separate Story and PR for all bugs
- User-facing bugs require alignment with Product
  - Dev-only bugs can be handled by the dev team


## Choosing Dependencies

We will choose Dependencies that are Stable Active and Well maintained

- Is it active/maintained, to qualify as active/maintained it should meet these criteria:
  _ The last commit was within one year to date.
  _ How many contributors, is there a company backing the project, or a whole community.
  _ Don't pull in branches contributed by only one developer
  _ How many open PRs? and is anybody reviewing them
- Is it stable? - How many open issues and how long do issues take before they are fixed.
- How many downloads, we want to find packages that have at least a couple thousand downloads
- follows semantic versioning MAJOR.MINOR.PATCH (e.g. 2.5.1)
  _ our `package.json` file should use the `^` will update the package to the latest patch and minor version.
  _ (e.g. `packageName: ^1.0.2`)
- License permits intended use
- It has quality documentation
- Avoid specific software version dependencies
