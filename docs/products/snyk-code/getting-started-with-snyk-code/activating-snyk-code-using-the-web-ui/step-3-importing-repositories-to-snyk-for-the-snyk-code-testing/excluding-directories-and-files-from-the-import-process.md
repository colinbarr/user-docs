# Excluding directories and files from the import process



When you import a repository to be tested by Snyk Code, you can exclude certain directories and files from the import by using the .**snyk** file. The .snyk file is a YAML policy file that can contain shell matching patterns (regular expressions), which allow you to specify the directories and files you want to exclude from the import process. The .snyk file should be created in the repository you intend to import.  &#x20;

<mark style="color:red;">**Important!**</mark>

* <mark style="color:red;">In Snyk Code, the .snyk file can ONLY be used for excluding directories and files from import. It CANNOT be used to ignore vulnerabilities or for any other action as in other Snyk products.</mark>
* <mark style="color:red;">Currently, the Exclude option in the .snyk file is applicable to the Snyk Web UI Environment only. It is NOT applicable to working with Snyk Code via the CLI and IDE Environments.</mark>

### **The exclusion syntax of the .snyk file**

**Use the following syntax to exclude files and directories via the `.snyk` file:**

<mark style="color:green;"># Snyk (https://snyk.io) policy file</mark>

exclude:

<mark style="color:green;"># Use either “</mark><mark style="color:green;">**global**</mark><mark style="color:green;">” or “</mark><mark style="color:green;">**code**</mark><mark style="color:green;">”. “</mark><mark style="color:green;">**global**</mark><mark style="color:green;">” applies to all Snyk products, and will exclude the specified directories and files from all Snyk tests; “</mark><mark style="color:green;">**code**</mark><mark style="color:green;">” applies only to the Snyk Code analysis.</mark> &#x20;

&#x20;global:

&#x20; <mark style="color:green;"># Exclude a single file. For example, - test.spec.ts</mark>

&#x20;  \- file\_name.ext

&#x20; <mark style="color:green;"># Exclude a single directory. For example, - src/lib</mark>

&#x20;  \- source/directory\_name

&#x20; <mark style="color:green;"># Exclude any file with a specific extension in the specific directory. For example, - tests/\*.ts</mark>

&#x20;  \- directory\_name/\*.ext

&#x20;  <mark style="color:green;"># Exclude files with a specific ending in any directory. For example, - “\*\*/\*.spec.ts”</mark>

&#x20;  \- “\*\*/\*.ending.ext”

&#x20; <mark style="color:green;"># Exclude files in directories that have the same name with a different ending, like “test” and “tests”. The last character before the question mark is optional.  For example, - tests?/\*</mark>

&#x20;  \- directory\_name?/\*

&#x20;  <mark style="color:green;"># Exclude all files and directories in a specific directory. For example, - tests/\*\*</mark>

&#x20;  \- directory\_name/\*\*

**Notes**:

* The path in the rule should be relative to the .snyk file location.
* All rules must have a preceding dash to be valid: - \<Exclusion\_rule>
* Any rule beginning with an asterisk must be wrapped in quotes. For example:\
  \- ”\*/src”
* When using the syntax in the .snyk YAML file, pay careful attention to new lines and their indentation. Using the wrong indentation will prevent the execution of your excluding specification. To verify that you are using the syntax correctly, you can use a YAML Validator, like the [Code Beautify Org Validator](https://codebeautify.org/yaml-validator). &#x20;
* For more information on the syntax of shell matching patterns, see for example:
  * GNU Org - [Shell Pattern Matching](https://www.gnu.org/software/findutils/manual/html\_node/find\_html/Shell-Pattern-Matching.html)
  * Docstore - [Pattern Matching Quick Reference with Examples](https://docstore.mik.ua/orelly/unix/upt/ch26\_10.htm)

&#x20;

### **Using the .snyk File to exclude directories and files from import**

**To exclude directories and files from the import process using the .snyk file:**

1\.  On the repository you want to import, create a YAML file called “.**snyk**”.

For example:

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - .snyk file creation - 2.png>)

2\.  On the .snyk file, specify the directories and/or files you want to exclude from import according to the following syntax:

```
// # Snyk (https://snyk.io) policy file
exclude:
 global:
   - <Exclusion_rule>
   - <Exclusion_rule>
```

For example:

```
// # Snyk (https://snyk.io) policy file
exclude:
 global:
   - todolist-goof/** 
```

&#x20; 3\.  From the Snyk Web UI, import your repository by one of the following ways:

* If the repository was already imported to Snyk – retest the repository as follows:
  * On the **Projects** page, click the **Code analysis** Project of the repository. Then, on the **Code Analysis** page, click the **Retest now** option below the header: &#x20;

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - Retest option.png>)

* If the repository was not imported yet to Snyk – [import the repository](importing-additional-repositories-to-snyk.md).

Your repository is imported to Snyk, without the directories and/or files you selected to exclude.

&#x20;****&#x20;

### **Example**: **Excluding 2 files from the Snyk Code analysis**

We have a repository called “**snyk-goof**”, which we want to test for vulnerabilities using Snyk Code. After we imported this repository to Snyk, we get a list of 10 detected vulnerability issues, which were found in 3 files:

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - Example - Before Exclude.png>)

Now we want to exclude the **app.js** and **db.js** files from the Snyk Code analysis. To achieve that, we perform the following:

1\.  We create a **.snyk** file in the **snyk-goof** repository in GitHub:

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - Example - .snyk file creation.png>)

2\.  In the .snyk file, we enter the following commands to exclude the **app.js** and **db.js** files from the import:

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - Example - Command.png>)

3\.  We retest the **snyk-goof** repository, by clicking the **Retest now** option on the **Code Analysis** page of the repository:

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - Example - Retest option.png>)

The **app.js** and **db.js** files are excluded from the retest, and therefore are not tested by Snyk Code. For this reason, they do not appear in the Code Analysis results, and now only 5 vulnerability issues are detected:

![](<../../../../../.gitbook/assets/Snyk Code - Exlude from Import - Example - Results.png>)
