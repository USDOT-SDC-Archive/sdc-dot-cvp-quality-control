[![Build Status](https://travis-ci.com/usdot-jpo-sdc/sdc-dot-cvp-quality-control.svg?branch=master)](https://travis-ci.com/usdot-jpo-sdc/sdc-dot-cvp-quality-control)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=usdot-jpo-sdc-dot-cvp-quality-control&metric=alert_status)](https://sonarcloud.io/dashboard?id=usdot-jpo-sdc-dot-cvp-quality-control)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=usdot-jpo-sdc-dot-cvp-quality-control&metric=coverage)](https://sonarcloud.io/dashboard?id=usdot-jpo-sdc-dot-cvp-quality-control)

# sdc-dot-cvp-quality-control

US Department of Transportation (USDOT) Intelligent Transportation Systems Secure Data Commons (ITS SDC). Connected Vehicle Pilots (CVP) data quality control and verification tools.

The Secure Data Commons (SDC) is a cloud-based analytics platform that enables access to traffic engineers, researchers, and data scientists to various transportation related datasets. The SDC platform is a prototype created as part of the U.S. Department of Transportation (USDOT) research project.  The objective of this prototype is to provide a secure platform, which will enable USDOT and the broader transportation sector to share and collaborate their research, tools, algorithms, analysis, and more around sensitive datasets using modern, commercially available tools without the need to install tools or software locally.  Secure Data Commons (SDC) enables collaborative but controlled integration and analysis of research data at the moderate sensitivity level (PII & CBI).

Please see README to the [sdc-dot-cvp-ingest](https://github.com/usdot-jpo-sdc/sdc-dot-cvp-ingest) repository for more information about the SDC Platform.

<!---                           -->
<!---     Table of Contents     -->
<!---                           -->
## Table of Contents

[I. Release Notes](#release-notes)

[II. Usage Example](#usage-example)

[III. Configuration](#configuration)

[IV. Installation](#installation)

[V. Design and Architecture](#design-architecture)

[VI. Unit Tests](#unit-tests)

[VII.  File Manifest](#file-manifest)

[VIII.  Development Setup](#development-setup)

[IX.  Release History](#release-history)

[X. Contact Information](#contact-information)

[XI. Contributing](#contributing)

[XII. Known Bugs](#known-bugs)

[XIII. Credits and Acknowledgment](#credits-and-acknowledgement)

[XIV.  CODE.GOV Registration Info](#code-gov-registration-info)


<!---                           -->
<!---     Release Notes         -->
<!---                           -->

<a name="release-notes"/>

## I. Release Notes


<!---                           -->
<!---     Usage Example         -->
<!---                           -->

<a name="usage-example"/>

## II. Usage Example



<!---                           -->
<!---     Configuration         -->
<!---                           -->

<a name="configuration"/>

## III. Configuration


<!---                           -->
<!---     Installation          -->
<!---                           -->

<a name="installation"/>

## IV. Installation


<!---                                 -->
<!---     Design and Architecture     -->
<!---                                 -->

<a name="design-architecture"/>

## V. Design and Architecture

### Data Ingest Quality Control
The following diagram represents data ingest flow with elements of data quality control:

![SDC Quality_Control](https://github.com/usdot-jpo-sdc/sdc-dot-cvp-staging/blob/master/images/data_quality_control.png)

Overall, the intent of tools tracked with this sdc-dot-cvp-quality-control repository is to ensure data consistency from upload by data providers through the Data Lake and into the Data Warehouse.

There are 3 message counts currently being captured:
* Data Providers upload files with message count for each uploaded data set
* Lambda function automation parses uploaded data files and counts the number of messages in each file
* Shell scripts count the number of records loaded into the Data Warehouse.

These counts then independently uploaded into Elastic Search service and become available for cross-verification. Amazon CloudWatch alarms are triggered if any of the counts for a given set of messages do not match with each other.

For decoupling purposes, all Lambdas are invoked via SNS Topics. Topics are not shown in the diagram for clarity.


<!---                           -->
<!---     Unit Tests          -->
<!---                           -->

<a name="unit-tests"/>

## VI. Unit Tests




<!---                           -->
<!---     File Manifest         -->
<!---                           -->

<a name="file-manifest"/>

## VII. File Manifest


<!---                           -->
<!---     Development Setup     -->
<!---                           -->

<a name="development-setup"/>

## VIII. Development Setup

### Prerequisites



<!---                           -->
<!---     Release History       -->
<!---                           -->

<a name="release-history"/>

## IX. Release History


<!---                             -->
<!---     Contact Information     -->
<!---                             -->

<a name="contact-information"/>

## X. Contact Information

<!-- Your Name – @YourTwitter – YourEmail@example.com
Distributed under the XYZ license. See LICENSE for more information.
https://github.com/yourname/github-link -->

For any queries you can reach to support@securedatacommons.com


<!---                           -->
<!---     Contributing          -->
<!---                           -->

<a name="contributing"/>

## XI. Contributing


<!---                           -->
<!---     Known Bugs            -->
<!---                           -->

<a name="known-bugs"/>

## XII. Known Bugs


<!---                                    -->
<!---     Credits and Acknowledgment     -->
<!---                                    -->

<a name="credits-and-acknowledgement"/>

## XIII. Credits and Acknowledgment
Thank you to the Department of Transportation for funding to develop this project.


<!---                                    -->
<!---     CODE.GOV Registration Info     -->
<!---                                    -->

<a name="code-gov-registration-info">

## XIV. CODE.GOV Registration Info
Agency:  DOT

Short Description:  US Department of Transportation (USDOT) Intelligent Transportation Systems Secure Data Commons (ITS SDC). Connected Vehicle Pilots (CVP) data quality control and verification tools.

Status: Beta

Tags: transportation, connected vehicles, intelligent transportation systems

Labor Hours:

Contact Name: support@securedatacommons.com

<!-- Contact Phone: -->
