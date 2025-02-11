# Test your configuration files

With Snyk Infrastructure as Code, you can test your configuration files with the CLI. For information on how to use the `snyk iac test command`, see the information on this page. For details about testing the various configuration files see the following pages:

* [Test your Terraform files with Snyk CLI](test-your-terraform-files-with-the-cli-tool.md)
* [Test your CloudFormation files with Snyk CLI](test-your-cloudformation-files-with-cli-tool.md)
* [Test your AWS CDK files with Snyk CLI](test-your-aws-cdk-files-with-our-cli-tool.md)
* [Test your Kubernetes files with Snyk CLI](test-your-kubernetes-files-with-our-cli-tool.md)
* [Test your ARM files with Snyk CLI](test-your-arm-files-with-the-cli-tool.md)

{% hint style="info" %}
As of CLI version 1.594.0 all configuration files are processed locally, ensuring that they do not leave your machine. Earlier versions by default send the configuration files to Snyk to be processed. Snyk recommends that you upgrade to the latest version of the CLI.
{% endhint %}

In the examples that follow, you can replace `main.tf` with your filename, for example, `deployment.yaml`.

## Test for an issue on specified files

Usage:

```
snyk iac test
```

Example:

```
snyk iac test main.tf
```

You can also specify multiple files by appending the file names after each other, for example:

```
snyk iac test file-1.tf file-2.tf
```

## Test for an issue on a directory of files

You can scan a directory of configuration files. This scans recursively through all files and folders.

Example, scan all directories relative to your current path:

```
snyk iac test
```

Example, scan a specific folder:

```
snyk iac test my-folder
```

Example, restrict the directory depth to be scanned:

```
snyk iac test --detection-depth=3
```

This limits the search to the specified directory (or current directory if no `PATH` provided) plus two levels of subdirectories.

## Output the test format as JSON

Usage:

```
snyk iac test  --json
```

This can be helpful if you want to store a snapshot of the results locally, or process the results in another tool for reporting and further analysis.

Example:

```
snyk iac test main.tf --json
```

## Output the test format as SARIF

SARIF is an open standard for the output of static analysis tools. You can view and save the results of your tests as a SARIF file for analysis in another tool.

Usage:

```
snyk iac test main.tf --sarif
```

To save this to a file output, you can run:

```
snyk iac test main.tf --sarif-file-output=snyk.sarif
```

## Display issues only above a specific severity level

Usage:

```
snyk iac test  --severity-threshold=medium
```

Example:

```
snyk iac test main.tf --severity-threshold=medium
```

This displays only results that have a severity value of medium or higher.

## Target a specific Snyk organization

You can control the severity settings of your security rules at the organization level in the Snyk UI. By targeting a specific organization in your CLI tests, you can determine which rules should be run and the severity of them.

Usage:

```
snyk iac test  --org=infrastructure
```

Example:

```
snyk iac test main.tf --org=infrastructure
```

You can also set the `org` flag in `snyk config`, so you do not need to use the `--org` option each time you want to specify the organization.

```
snyk config set org=infrastructure
```
