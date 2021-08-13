# Jira

**Feature availability**  
This feature is available with all paid plans. See [pricing plans](https://snyk.io/plans/) for more details.

#### **Set up your Jira integration**

Our Jira integration allows you to manually raise Jira issues in the Snyk UI for vulnerabilities or license issues, and also includes an API \([see our API docs](https://snyk.docs.apiary.io/#reference/projects/project-jira-issues)\).

### Caution

if your Jira instance is private, you'll need to set up with Snyk Broker and then follow our brokered Jira setup instructions.

**How to set up your Jira integration**

To connect your Snyk account to your Jira account, go to the integrations page in your organization settings and type in your credentials. We recommend setting up a new user in Jira for this, rather than using existing credentials. You can authenticate by username and password, but we recommend authenticating by API token which you can generate from [Atlassian API tokens](https://id.atlassian.com/manage/api-tokens).

Once you’ve set up the connection, visit one of your Snyk projects. You’ll now see a new button at the bottom of each vulnerability and license issue card that allows you to create a Jira issue.

![image1.png](https://support.snyk.io/hc/article_attachments/360007146558/uuid-07abf9db-45cb-cdcd-537b-328a0c4b891e-en.png)

When you click on this, a Jira issue creation form will appear with the Snyk issue details copied across into the relevant fields. You can review and edit this before creating the issue.

Select which Jira project you’d like to send the issue to. The fields that we display below are based on the fields that the project has, so switching between projects may show different options.

**Note:** Snyk currently supports non-Epic Jira ticket creation. Epics will need to be added manually to the ticket once it has been created.

![image2.png](https://support.snyk.io/hc/article_attachments/360007146578/uuid-67202f8e-7f70-1e84-6044-f65ec36138b3-en.png)

Once you’ve created a Jira issue, the Jira key with a link will display on the issue card. If you’re using the Jira API, you can generate multiple Jira issues for the same issue in Snyk.

![image3.png](https://support.snyk.io/hc/article_attachments/360007065057/uuid-5283ddbe-913b-1aa1-ec74-e384b0e2929b-en.png)

You can also see which Jira issues have been created from the Issues view in your reports.

![image4.png](https://support.snyk.io/hc/article_attachments/360007146598/uuid-cd4e8cae-2528-a922-5a03-5f23c42d4ac2-en.png)

### See also:

[Enable permissions for Snyk Broker from your third-party tool](https://support.snyk.io/hc/en-us/articles/360015296737-Enable-permissions-for-Snyk-Broker-from-your-third-party-tool)
