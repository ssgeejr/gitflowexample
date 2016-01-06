# GitFlowExample
Sample project to show how GitFlow works

Check the branches menu, top left.

You will see three branches
  # master
  # develop
  # issue-21
  
## Each branch has different purposes

**Master** is your read to go, passed all QA code base - this is the code you branch to REL-201601.01 (or the likeness there of)

**Develop** is your constantly changing and churning base - when multiple repositories are in play, an individual project may pass all QA testing, but might not still work in the greater eco-system when merged with other functions.
For example, my php-code is fine and passes all QA/Unit testing. However, when I deploy it, it fails ... debugging will show that the issue is in some (fictious) web-server call that resides in another project.

**issue-21** this is where I track the work being worked on 'now'


## How do the branches work together? 
once I'm done coding on issue-21, I create a pull-request from issue-21 to develop. This pull request will (it doesn't but this is an example) trigger a small 'micro-test' that will be executed on TravisCI (https://travis-ci.org/) ... *see the 'ShellRaptor' project for actual working TravisCI integration* - if that passes, the PR is updated and can be merged

Once everyone has passed issue-level QA tests and we are happy with what we have, it is time to merge develop into master.  Open a pull-request to merge develop into master.  At this time, a full scale ecosystem test is ran (again, it wont be - we're just talking shop here) to verify ALL components fit together and play nice.  If that test succedes, it is safe to merge into Master as we know nothing will be broken.

That's about it ... good luck and good programming


