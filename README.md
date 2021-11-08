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

```yaml
    - name: Update JIRA status
      uses: The-ring-io/update_jira_issue@v1
      with:
        # This is value containing the github reference that contains your banch name
        # Should be pretty much all the time the value in the example below
        git-ref: ${GITHUB_REF#refs/heads/}
        # This is the base URL of your company's JIRA server like https://the-ring-io.atlassian.net/
        jira-base-url: ${{ secrets.JIRA_BASE_URL }}
        # This is the JIRA Api token value, used for the webservice calls made to change issue statuses
        # See https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/ 
        jira-api-token: ${{ secrets.JIRA_API_TOKEN }}
        # This is the user email address associated 
        jira-user-email: ${{ secrets.JIRA_USER_EMAIL }} 
        # This is the name of the new status you want to set
        jira-status: 'Dev in progress'
```