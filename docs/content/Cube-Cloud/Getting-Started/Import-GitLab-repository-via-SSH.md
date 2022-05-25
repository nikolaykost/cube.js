---
title: 'Getting Started with Cube Cloud: Import GitLab repository via SSH'
permalink: /cloud/getting-started/gitlab/ssh
---

This guide walks you through creating a new deployment on Cube Cloud from a
[GitLab][gitlab] repository via SSH.

## Step 1: Create an account

Navigate to [cubecloud.dev](https://cubecloud.dev/), and create a new Cube Cloud
account.

## Step 2: Create a new Deployment

Click the `Create Deployment` button. This is the first step in the deployment
creation. Give it a name and select the cloud provider and region of your
choice.

<div
  style="text-align: center"
>
  <img
    alt="Cube Cloud Create Deployment Screen"
    src="https://cubedev-blog-images.s3.us-east-2.amazonaws.com/f5b73cc7-ac72-49ff-a3cd-491c6ab89bbc.png"
    style="border: none"
    width="100%"
  />
</div>

## Step 3: Import Git repository

Next up, the second step in creating a Cube App from scratch in Cube Cloud is to
click the `Import Git repository via SSH` button.

<div
  style="text-align: center"
>
  <img
  alt="Cube Cloud Upload Project Screen"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/cube-cloud-upload-project-screen.png"
  style="border: none"
  width="100%"
  />
</div>

Now go to your GitLab repository and from the `Clone` dropdown menu, copy the
`Clone with SSH` URL:

<div
  style="text-align: center"
>
  <img
  alt="Getting the repository's SSH URL from GitLab"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/gitlab-get-ssh-url.png"
  style="border: none"
  width="100%"
  />
</div>

Back in Cube Cloud, paste the URL and click `Generate SSH key`:

<div
  style="text-align: center"
>
  <img
  alt="Getting SSH key from Cube Cloud"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/getting-ssh-key-from-cube-cloud.png"
  style="border: none"
  width="100%"
  />
</div>

Now copy the SSH key and go back to GitLab and into the repository's settings.
Find the `Deploy keys` section and click `Expand`. Give the key a title
(`Cube Cloud`, for example) and paste the SSH key in the relevant field:

<div
  style="text-align: center"
>
  <img
  alt="Add Cube Cloud deploy key to GitLab"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/gitlab-add-deploy-key.png"
  style="border: none"
  width="100%"
  />
</div>

Ensure `Grant write permissions to this key` is checked, then click `Add key`.
Go back to Cube Cloud and click `Connect`. After a connection is successfully
established, you should see the next screen:

<div
  style="text-align: center"
>
  <img
  alt="Getting webhook URL from Cube Cloud"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/cube-cloud-get-webhook-url.png"
  style="border: none"
  width="100%"
  />
</div>

Copy the `Cube Cloud Git Webhook URL` and go to your GitLab project's `Webhooks`
settings. Paste the URL into the correct field, ensure the `Push events` trigger
is checked and click `Add webhook`.

<div
  style="text-align: center"
>
  <img
  alt="Add Cube Cloud webhook to GitLab"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/gitlab-add-webhook.png"
  style="border: none"
  width="100%"
  />
</div>

Back in Cube Cloud, click `Connect` to test the webhook.

## Step 4: Connect your Database

Enter your credentials to connect to your database. Check the [connecting to
databases][link-connecting-to-databases] guide for more details.

<div
  style="text-align: center"
>
  <img
  alt="Cube Cloud Setup Database Screen"
  src="https://cubedev-blog-images.s3.us-east-2.amazonaws.com/1375f9f1-0860-412a-a436-e2e775ec10fa.png"
  style="border: none"
  width="100%"
  />
</div>

### Want to use a sample database instead?

We also have a sample database where you can try out Cube Cloud.

```json
Hostname
demo-db.cube.dev

Port
5432

Database
ecom

Username
cube

Password
12345
```

In the UI it'll look exactly like the image below.

<div
  style="text-align: center"
>
  <img
  alt="Cube Cloud Setup Database Screen"
  src="https://cubedev-blog-images.s3.us-east-2.amazonaws.com/031bb948-d706-412c-b714-5bf28df01312.png"
  style="border: none"
  width="100%"
  />
</div>

If you run into issues here, make sure to allow the Cube Cloud IPs to access
your database. This means you need to enable these IPs in your firewall. If you
are using AWS, this would mean adding a security group with allowed IPs.

## Step 5: Generate the Data Schema

Step four in this case consists of generating a data schema. Start by selecting
the database tables to generate the data schema from, then hit `generate`.

<div
  style="text-align: center"
>
  <img
  alt="Cube Cloud Setup Database Screen"
  src="https://cubedev-blog-images.s3.us-east-2.amazonaws.com/a906434b-c4da-414a-adb3-f010b1fa45d1.png"
  style="border: none"
  width="100%"
  />
</div>

Cube Cloud will generate the data schema and spin up your Cube deployment. With
this, you're done. You've created a Cube deployment, configured a database
connection, and generated a data schema!

<div
  style="text-align: center"
>
  <img
  alt="Cube Cloud Setup Database Screen"
  src="https://cubedev-blog-images.s3.us-east-2.amazonaws.com/b6addada-cc77-4940-aa0c-a0a9c3df6fd1.png"
  style="border: none"
  width="100%"
  />
</div>

You're ready for the last step, running queries in the Playground.

## Step 6: Try out Cube Cloud

Now you can navigate to Playground to try out your queries or connect your
application to Cube Cloud API.

<div
  style="text-align: center"
>
  <img
  alt="Cube Cloud Playground"
  src="https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/Cube-Cloud/getting-started-4.png"
  style="border: none"
  width="100%"
  />
</div>

[gitlab]: https://gitlab.com/
[link-connecting-to-databases]: /cloud/configuration/connecting-to-databases
