---
title: 'Switching from hourly to monthly billing'
excerpt: 'Find out how to change the billing rate for your Public Cloud instance'
slug: change-public-cloud-billing-rate
section: Project management
order: 4
---

**Last updated 6th December 2019**

## Objective

When you create a Public Cloud instance, you can choose to be billed at either an hourly or monthly rate. Hourly-rate instances are billed on a pay-as-you-go basis, i.e. at the end of the month, users are billed for the specific resources they have utilised. Monthly-rate instances can be paid for in advance, and are billed at a lower price (50% less than pay-as-you-go). If you initially selected hourly billing, you can switch to monthly billing at any time.

**This guide explains how to switch from hourly to monthly billing.**

> [!warning]
>
> You cannot switch from monthly to hourly billing. If you would like to be billed at the hourly rate, you will need to delete your monthly-rate billing instance, create a new one, and select hourly billing. In this case we suggest that you do the following procedure:
>
>- Create a snapshot of your current instance;
>
>- Create a new instance based on this snapshot;
>
>- Delete monthly instance.
>

## Requirements

- You need to have created a [Public Cloud instance](www.ovh.com/world/public-cloud/instances/){.external}.
- You must be logged in to the [OVHcloud Control Panel](https://ca.ovh.com/auth/?action=gotomanager){.external}.


## Instructions

In the [Control Panel](https://ca.ovh.com/auth/?action=gotomanager){.external}, choose the instance you would like to change the billing rate for, and open its options menu by clicking on the 3 dots on the right of the Instance. You will then be able to see the `Switch to monthly subscription`{.action} button:

![Change billing calculation](images/switch.png){.thumbnail}

You will then need to confirm that you want to change the billing rate:

![Confirm billing calculation change](images/switch1.png){.thumbnail}

Once you have confirmed your choice, your next bill will include the hourly cost of the instance for the remaining days of the month, along with the cost for the next month at the monthly flat rate.


## Go further

Join our community of users on <https://community.ovh.com/en/>.
