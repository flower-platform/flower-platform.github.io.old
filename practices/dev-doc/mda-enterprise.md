---
layout: page
group: subconcept
parent-id: dev-doc

title: "Using Flower Platform MDA Enterprise"
#tagline: "tagline"
comments: true
share: true
# in case you want to force a disqus identifier, when you rename the page
# get the disqus identifier from the original page (something like var disqus_identifier = 'ident';),
# uncomment the following line and replace the text between "" with ident
#comments_identifier: "identifier"
---
{% include JB/setup %}

After generating the application following the MDA flow, we are ready to deploy it to our servlet container, using the deploy interface.

<!-- more -->

We will create three jobs, one for each step of the process: building the application, uploading to a remote machine and deploying to our servlet container.

<img class="img-thumbnail center-block" src="job-status.png"/>

## Build job

The build job is a simple job, with a custom workspace, pointing to the location of the generated project.

<img class="img-thumbnail center-block" src="job-build.png"/>

We add a build step which will invoke Maven. The project will be packaged as a ``.war`` file, ready to upload and deploy to our servlet container.

<img class="img-thumbnail center-block" src="job-build-step.png"/>

## Upload job

The upload job will invoke the ``upload`` target. We specify a properties file with our remote host information, and the name of the package that was previously built.

<img class="img-thumbnail center-block" src="job-upload.png"/>

We can also set the upload job to run automatically after the build job.

<img class="img-thumbnail center-block" src="job-upload-trigger.png"/>

## Deploy job

The deploy job will invoke the ``deploy`` target. The configuration is the same as for the upload job above. This job will deploy the newly uploaded package and restart our servlet container.

<img class="img-thumbnail center-block" src="job-deploy.png"/>

Similarly, the deploy job may be set to run automatically after the upload job.

<img class="img-thumbnail center-block" src="job-deploy-trigger.png"/>

The application is now available in our servlet container.

<img class="img-thumbnail center-block" src="app.png"/>