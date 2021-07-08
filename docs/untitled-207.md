# Scan and fix security issues in your Terraform  files

* [ Configure your integration to find security issues in your Terraform files](/hc/en-us/articles/360011018938-Configure-your-integration-to-find-security-issues-in-your-Terraform-files)
* [ Scan and fix security issues in your Terraform files](/hc/en-us/articles/360010916577-Scan-and-fix-security-issues-in-your-Terraform-files)
* [ Detecting Terraform configuration files using a broker](/hc/en-us/articles/360011018778-Detecting-Terraform-configuration-files-using-a-broker)

##  Scan and fix security issues in your Terraform files

Snyk scans your Terraform code for misconfigurations and security issues as well. For configuration files, once scanned, Snyk reports on any misconfigurations based on the settings your administrator has implemented, and makes recommendations for fixing accordingly.

### Prerequisites

* An administrator should integrate your organization with your preferred Git repository and enable detection of configuration files as described [here](https://support.snyk.io/hc/en-us/articles/360011018938-Configure-your-integration-to-find-security-issues-in-your-Terraform-files).
* You must have a Snyk account and your Terraform files should be in `.tf` format.
* We currently detect AWS, Azure and GCP related security issues.

### Scan and fix your configuration files

1. 2. If you already imported your repositories for testing before the infrastructure as code feature was enabled by your administrator, then you should re-import that repository in order to detect the Terraform code:
3. Every time a repository is scanned:
   * Every Terraform file is imported as a separate project, grouped together per repository, similar to this example:
   * If you re-imported the repository in order to import the Terraform files, then Snyk imports and re-tests the already imported application manifest files - displaying the test time as "now".
4. Click the project link you're interested in, to view the scan results and to help correct your Terraform code: 
