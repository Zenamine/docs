---
title: Monitoring your jobs using Grafana and the Apache Spark dashboard 
slug: monitor
excerpt: Find out how to monitor your jobs using Grafana and the Apache Spark dashboard
section: Getting started
order: 2
---

**Last updated 06<sup>th</sup> March, 2020**

## Objective

This guide will tell you how you can monitor you jobs after submitting them. 

In this guide, we are assuming that you're using the [OVHcloud Manager](https://ca.ovh.com/auth/?action=gotomanager){.external} to use the Data Processing platform and you have already submitted a job. 

To read an introduction about Data Processing service you can visit [Data Processing Overview](../overview){.external}.

## Requirements 

- Access to the [OVHcloud Manager](https://ca.ovh.com/auth/?action=gotomanager){.external}
- A job that has been already submitted to Data Processing

## Instructions

### Apache Spark Dashboard 

After submitting your job, follow these steps to open its Apache Spark dashboard: 

- Find your job in the list of jobs in the Data Processing page of the OVHcloud Manager.
- Click on the name of the job to open its dashboard. 

![Data Processing Job dashboard](images/jobuserinterface.png){.thumbnail}

- Click on  `Open job user interface`{.action} in the **Actions** panel to open the Apache Spark dashboard. If you do this right after submitting a job, you will see a warm up page for a few seconds while your job is starting. 

![Warming up](images/warmup.png){.thumbnail}

The Apache Spark dashboard for your job will then start automatically. 

![Apache Spark dashboard](images/sparkdashboard.png){.thumbnail}

### Grafana Dashboard

After you submit a job to the Data Processing platform, follow these steps to monitor your job using a Grafana dashboard. 

- Find your job in the list of jobs in the Data Processing page in the OVHcloud Manager.
- Click on the name of the job to open its dashboard. 
- In the dashboard, click on `Monitor job`{.action} in the **Actions** panel. 

![Metrics token](images/token.png){.thumbnail}

- Copy the metrics token that is now displayed in the popup. 
- Open [https://grafana.com/grafana/dashboards/11844](https://grafana.com/grafana/dashboards/11844) and copy the Grafana ID by clicking the button `Copy ID to Clipboard`{.action}
- Open [https://grafana.metrics.ovh.net/login](https://grafana.metrics.ovh.net/login) and login with your OVHcloud account. 
- From the main menu, click `Dashboards`{.action} -> `Import`{.action}

![grafana](images/grafana.png){.thumbnail}

- In the import dashboard page, paste the Grafana ID that you copied before and click on the `Load`{.action} button. 

![grafana import](images/import.png){.thumbnail}

- Write a name for your dashboard 
- Paste the metrics token that you copied before. 
- For *datasource*, select `My Data Source 1`{.action} from the menu.
- Click on the `Import`{.action} button to open your dashboard. 

![grafana import](images/import2.png){.thumbnail}

- You can now select a job ID from the list of all the jobs you have submitted so far to see its Grafana dashboard. 

![grafana charts](images/grafanacharts.png){.thumbnail}

## Go further

To learn more about using Data Processing and how to create cluster and process your data, we invite you to look at [Data Processing documentations page](../).

You can send your questions, suggestions or feedbacks in our community of users on [https://community.ovh.com/en/](https://community.ovh.com/en/){.external} or in our public [Gitter](https://gitter.im/ovh/data-processing){.external}
