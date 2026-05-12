> [!CAUTION]
> This repository is archived and not used anymore. See https://github.com/jenkins-infra/helpdesk/issues/5098 for details.

**Finds and reports unused code in Jenkins api** (including in latest published plugins and potential usage in jelly files, except getters, setters and fields, except deprecated classes and methods, except unit tests)

[![Build Status](https://ci.jenkins-ci.org/buildStatus/icon?job=Reporting/infra_deprecated-usage-in-plugins)](https://ci.jenkins-ci.org/view/All/job/Reporting/job/infra_unused-code-detector/)

Current results in summary:
* 1096 plugins
* 198 Jenkins methods are detected as not used in the latest published plugins and in core

See details in the [continuous integration](https://ci.jenkins-ci.org/view/All/job/Reporting/job/infra_unused-code-detector/lastSuccessfulBuild/artifact/target/output.html)
or in this [example of output](../../blob/master/Output_example.html).

There are certainly false positives and there are unused methods missing in the report.
To be sure that a method is never used, you can [grep all sources](https://wiki.jenkins-ci.org/display/JENKINS/Grepping+all+sources) or [search in github](https://github.com/search?type=Code&q=user%3Ajenkinsci+SomeClass.staticMethod) directly.

See also:
* Unused deprecated classes, methods and fields are listed in the [deprecated-usage-in-plugins job](https://ci.jenkins-ci.org/view/All/job/Reporting/job/infra_deprecated-usage-in-plugins/lastSuccessfulBuild/artifact/target/output.html#deprecatedApiNotUsed) using [this tool](https://github.com/jenkins-infra/deprecated-usage-in-plugins)
* [Jenkins policy for API deprecation](https://issues.jenkins-ci.org/browse/JENKINS-31035)

To run the tool yourself : Checkout and run with "mvn clean compile exec:java".
Note: it is quite long to download all the plugins the first time (1.8 GB).

[License MIT](../../blob/master/LICENSE.txt)

Author Emeric Vernat
