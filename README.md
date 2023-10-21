# Frontend Alpha Release Process

## Overview

This document provides instructions on:

1. Deploying KnoWhiz's front-end application using Vercel.
2. Creating a custom domain for the application using Vercel and AWS Route 53.

## Prerequisites
- A Vercel account
- Access to the project's Git repository
- Access to the project's AWS console

## Import the Project
1. Log into your Vercel account.
2. Click `Add New`, select `Project`, and import the git repository for the project

## Configure and Deploy the Project
1. Choose a project name. This will be your default domain name and can be anything, as we will customize the domain name later.
2. Choose `Next.js` as your framework.
3. Define any necessary environment variables.
- Note: In your source code and Vercel, environment variables to be made available in the browser should have the prefix `NEXT_PUBLIC_`. For example, `process.env.URL` will not be accessible in the client browser, but `process.env.NEXT_PUBLIC_URL` will.
4. Leave the rest as default values.
5. Click the `Deploy` button.

## Customize the Domain Name
### Actions on Vercel
1. In the project, go to `Settings` and select `Domains`
2. Add the custom domain name (e.g. `knowhiz.us`). Select `Add www.knowhiz.us and redirect knowhiz.us to it`. 
3. Scroll down to see the following. The value in the red box will be used next.
![1280X1280](https://github.com/david-hp-0726/knowhiz-frontend-doc/assets/120674894/b9b97fac-7356-4372-876e-42e07fbe5193)

### Actions on AWS
1. In the project, go to `Route 53 Dashboard` and select `Hosted zone`.
![image](https://github.com/david-hp-0726/knowhiz-frontend-doc/assets/120674894/9c0262d6-ab35-447a-b7e6-8c36d1248305)
2. In the `records` section, click `Create record`.
3. Put `www` for the record name, `[the above dns]` for value, leave the rest as their defaults, and then create the record. This would configure `www.knowhiz.us`.
![image](https://github.com/david-hp-0726/knowhiz-frontend-doc/assets/120674894/80b7f348-2036-4253-a6cc-081d21c5f0d4)
4. To configure `knowhiz.us`, repeat steps 1 through 3. In step 3, leave the record name blank, put `[the above dns]` for value, leave the rest as their defaults, and then create the record.
![image](https://github.com/david-hp-0726/knowhiz-frontend-doc/assets/120674894/2775ab97-9d0d-42ea-9b3b-12330f5c8bc8)


