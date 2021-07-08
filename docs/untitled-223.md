# Brinqa

* [ Code Dx Enterprise](/hc/en-us/articles/360018848798--Code-Dx-Enterprise)
* [ Brinqa](/hc/en-us/articles/360012728717-Brinqa)
* [ Fortify SSC integration](/hc/en-us/articles/360005507838-Fortify-SSC-integration)
* [ Kenna Security](/hc/en-us/articles/360013620217-Kenna-Security)
* [ Nucleus Security](/hc/en-us/articles/360012502818-Nucleus-Security)
* [ RiskSense](/hc/en-us/articles/360015069418-RiskSense)
* [ Vulcan-Cyber](/hc/en-us/articles/360012981478-Vulcan-Cyber)

##  Brinqa

### Introduction to Snyk and Brinqa Integration

Brinqa’s integration with Snyk makes it easy to incorporate your software composition analysis \(SCA\) data with your application risk management solution. Combining Snyk insights with data from asset management, threat intelligence, and varied sources of business context delivers an automated and effective solution for open source risk analysis, prioritization, remediation, and reporting.

### How it Works

**Note:** This integration relies on the Snyk API which is only available to paid Snyk plans. [Find out more about the API](https://snyk.docs.apiary.io/#), or [review your own plan and start a free trial](https://app.snyk.io/manage/billing) to experience the full value Snyk offers. 

1. Create a service account in snyk - [Service Accounts page](https://support.snyk.io/hc/en-us/articles/360004037597)
2. Open your Brinqa instance and navigate to Administration &gt; Data Integration &gt; Data Sources. Locate the Snyk connector listed in the ‘Application Security’ section. If you don’t see the connector listed, please contact your Brinqa account representative to enable the Snyk integration.
3. Click on the Snyk connector to configure your data source. Enter your API key in the allocated field. For additional details on configuring data sources please see Brinqa documentation \([http://docs.brinqa.io/data-integration/data-sources/](http://docs.brinqa.io/data-integration/data-sources/)\).
4. Once the data source is configured, you can map incoming Snyk data to existing or new Brinqa data models. For additional details on configuring data mapping please see Brinqa documentation \([http://docs.brinqa.io/data-integration/data-mapping/](http://docs.brinqa.io/data-integration/data-mapping/)\).
5. Once data source and data mapping configurations are completed, you can sync data manually or using scheduling syncs. For additional details on scheduling data syncs please see Brinqa documentation \([http://docs.brinqa.io/data-integration/scheduled-syncs/](http://docs.brinqa.io/data-integration/scheduled-syncs/)\).
6. Once connector data syncs are initiated, Snyk data will be available in the Brinqa UI within a few minutes. For details on how to display Snyk data within Brinqa, please see User Interface documentation \([http://docs.brinqa.io/user-interface/overview/](http://docs.brinqa.io/user-interface/overview/)\).
