# update_jira_issue
# How to use

In order to use this github action, your branch name has to comply to a specific naming convention:
- `XXXX/JIRA-00_My-branch-description`    
where `XXXX` is the folder name of your branch, like `feat` or `fix`   
`JIRA-00` is the issue ID of the JIRA issue you want to update, for example `MERGE-100` or `SHOPS-12`.

Note that the folder name is optional, so a branch named `JIRA-00_My-branch-description` will also work.   
**Remark**: Do **NOT** use the underscore `_` character in your branch description, as it is used as the delimiter between your branch name and the JIRA-ID value. Always use the `-` instead.

Then, call this JIRA action while providing a valid status you want your issue to be migrated to.

Example of call: