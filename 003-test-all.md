# Command to test all installed formula
## Introduction
While you can `brew test` a single formula, there is no way (that I am aware of)
to test multiple, or all, formula that are installed.

## Motivation
This functionality would be helpful for debugging and ensuring a clean and fully
functional homebrew enviornment.

This is also motivated due to formulas sometimes breaking after upgrading and
`brew clean`ing dependencies. I know that generally when a dependency is bumped
that dependents are supposed to get a build bump too, but there have certainly
been times where this has been missed.

This would make identifying that easier for large upgrades, allowing the user
to determine quickly which formulas they should `brew reinstall`. Sometimes
multiple days can go by in-between upgrading and noticing a broken binary, and
when it is finally noticed the user may not have internet or the time to
rebuild a tool. This is especially important for users who build from source.

## Proposed solution
Add a `--all-installed` flag to `brew test` that iterates through all formula
installed and returns a non-zero status upon the first failure.

## Detailed design
The details are unimportant and up to the brew authors. For example, if it is
a flag like `--all-installed` or `--test-installed`, or a different argument
altogether.

## Alternatives considered
This could also be added to `brew doctor` instead of `brew test`, depending on
how you expect users to need this command.
