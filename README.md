[![Build Status](https://travis-ci.com/usdot-jpo-sdc/sdc-dot-cvp-quality-control.svg?branch=master)](https://travis-ci.com/usdot-jpo-sdc/sdc-dot-cvp-quality-control)
# sdc-dot-cvp-quality-control
US Department of Transportation (USDOT) Intelligent Transportation Systems Secure Data Commons (ITS SDC). Connected Vehicle Pilots (CVP) data quality control and verification tools.

## Secure Data Commons - Introduction
Please see README to the [sdc-dot-cvp-ingest](https://github.com/usdot-jpo-sdc/sdc-dot-cvp-ingest) repository for a brief introduction to the SDC Platform.

## Data Ingest Quality Control
The following diagram represents data ingest flow with elements of data quality control:

![SDC Quality_Control](https://github.com/usdot-jpo-sdc/sdc-dot-cvp-staging/blob/master/images/data_quality_control.png)

Overall, the intent of tools tracked with this sdc-dot-cvp-quality-control repository is to ensure data consistency from upload by data providers through the Data Lake and into the Data Warehouse.

There are 3 message counts currently being captured:
* Data Providers upload files with message count for each uploaded data set
* Lambda function automation parses uploaded data files and counts the number of messages in each file
* Shell scripts count the number of records loaded into the Data Warehouse.

These counts then independently uploaded into Elastic Search service and become available for cross-verification. Amazon CloudWatch alarms are triggered if any of the counts for a given set of messages do not match with each other.

For decoupling purposes, all Lambdas are invoked via SNS Topics. Topics are not shown in the diagram for clarity.
