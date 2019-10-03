# Development Policies

In this document we introduce some development policies, such as:

- Do not commit directly to master branch. 
- Create a new branch.
- Make a pull request.
- Add two colleagues as reviewers.
- Run all tests before creating a pull request.

## Coding

### Code style

You must follow good code styles. 

### Testing

All code must have test. When writing tests, have in mind that:

- Your tests prove your code works. Try to write them first.
- Another developer will read your tests to understand what your code does. Keep them clean.
- Another developer will rely on your tests in order to avoid introducing bugs while refactoring. Test thoroughly!

These principles come mostly from Clean Code Book, Chapter 9.

## Branching Strategy

### Protected Branches

For the purposes of the development of the projects we will maintain only a long-term protected branch, the `master` branch.

### The `master` branch

The `master` branch is our protected branch of all development activities. The development of a new features, changes or fixes will have to be as follows:

1. Create a new branch from the `master`
2. Add a reasonable amount of `commits` that form the new feature, changes or fixes
3.  In case your branch is not updated, `merge master` into your branch to bring it up to date.
4. Push the branch and open a `pull request` targeting `master`.
5. Add new `commits` to address feedback of your collegues.
6. Use the operation of Github `squash and merge` feature to merge the branch back to `master`.

An important condition for before performing the last step of the branch strategy (which focuses on merging the new features, changes or fixes to the master branch) is detailed in the merge strategy.

## Merge Strategy

### Reviews

In order for a pull request to be merged, it must satisfy the following:

- The pull request must have tests.
- Unit tests must pass.
- Review and approval of two colleagues.

### Squash and merge

Graphically, the process of creating and merging PRs via *squash-and-merge* looks like the following:

```
new branch             +----A---B---C---D-- (deleted)
                      /                /
master          -----+----------------+-----E
```

The contribution is implemented on the new branch via commits `A`, `B`, `C`. When the contribution is complete, master is merged into the feature branch (commit `D`). Github's feature *squash-and-merge* creates then a commit `E` which brings the implemented changes to master. Notice that this is not a merge commit in the sense of git (commit `E` only has one parent), and the new branch is then abandoned/deleted.

## Commits

Every commit on the protected branch should consist of a good commit summary and a commit description.

### Commit summary

In order to have a better organization of commits, we recommend:

- Use the following format: `prefix: description`.
- Possible prefix: 
    - features: `feat`
    - fixes: `fix`
    - enhancements: `enh`
    - documentation: `doc`.
- Use the imperative mode in the `description`: fix or add instead of fixed or added.
- Use lowercase letters.

### Commit description

Please spend some time on a good commit description. So, some important points below:

- The description should describe your contribution as precise as possible.
- The description should begin with a capital character.
- The description should not only explain **what** has contributed, but also **why**.

## Pull Requests

Pull requests are the way features, changes in general and fixes are merged into protected branches. No user should directly push to any of the protected branches and should instead always use GitHub pull requests because code reviews are a crucial tool of collaboration.
