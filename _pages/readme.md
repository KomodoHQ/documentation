---
ID: 3
post_title: README.md
author: admin
post_date: 2016-09-16 10:19:09
post_excerpt: ""
layout: page
permalink: >
  http://documentation.komododigital.dev/sample-documents/readme/
published: true
sidebar:
  - ""
footer:
  - ""
header_title_bar:
  - ""
header_transparency:
  - ""
---
# Example README

## Below is an example README for use in a standard Komodo Project.

# Project: Project Title Project explanation. This section should detail the objectives of the project, what technologies have been used, and what a development might need to know in order to work on the project (eg 

`feature X is on hold in branch` - this should **always** be up to date. **Remember that the README.md file is a living document. It is never finished. Keep the details up to date.** 
## Key Configuration Options Live Site URL: 

`http://www.example.com/` Staging Site URL: `http://staging.example.com/` Development URL: `http://example.dev/` BitBucket Repo: `project-name` Hints for finding things in LastPass: `Username is xyz` Development hosts entries: `192.168.1.123 development.dev` 
## Initialisation Instructions for spinning up a local development version of the website/app. 

1.  Clone the repo to a new directory
2.  Use `vagrant up` or `ansible-playbook -s config.yml` to start the site. 
    > Note: Your vagrant or ansible configuration should automate the entire process of getting the website up and running, from downloading the base box to provisioning services, to pulling in and installing a database migration, to building the product. Whereever possible a developer should be able to run a single command and have a working version of the site.
3.  Supply scripts for accessing the watch process from outside of the box. 
    > A typical script would be 'gulp.sh' that contains a shell script that calls `vagrant ssh -c 'cd /var/www/; gulp watch'` on the vagrant box. This means the developer doesn't ever need to ssh in to the box to do things. The goal of the process should be that the site can be set up, modified, and deployed remotely.

## Build Details of the build process. This section shall include; 

1.  What technology the build chain uses (eg gulp, npm, make).
2.  What artefacts the build process produces (eg /var/www/dist/)
3.  What artefacts the build process does note produce (eg /wp-content/uploads/)

### Available Build commands Details of the build commands available, and how they should be used. This section shall include; 

1.  Watch and sync functions eg `gulp watch` that should be used during development
2.  Build functions eg `gulp build` that creates a final build

## Testing Details of the testing process. This section shall include details of the test runner, tests available, coverage tools, etc. 

### Automated tests (Karma, Nightwatch, etc)

1.  How to run the tests eg `gulp test` or `nightwatch -e chrome`
2.  Where test reports are stored eg `/var/www/logs/`

### Functional tests (Lantern, Browserstack, etc)

1.  How to run the tests eg `karma run`
2.  Where test reports are stored eg `/var/www/logs/`
3.  Where the test data is stored eg `/var/www/tests`

### Manual testing and test scripts Information about the website and what should be tested, including information about different browsers and operating systems. Include information about test user details (or how to find them in LastPass). Where the user test scripts are stored for eg 

`/var/www/tests/user`. 
> User test scripts are documented processes for achieving a specific result in an application. For example, if a user can log in to the site and change their user information then each necessary step should be written out as a script that the tester can follow. Testers need to know about *every* feature in a site in order to manually verify that the software works correctly. Do not assume anything is 'obvious' just because it's obvious to you. Ideally a tester should be able to print the user test scripts and go through them one by one, ticking off features as they go, and by the time they've ticked off every script we know for certain that the software is complete.
## Deployment Steps to deploy the website to staging or live. Make sure that this section is 

*very* detailed. This part is important. 
### Available deployment commands Any commands that are used to deploy the website should be documented. Eg 

`gulp deploy` or `npm deploy`. Deployment commands should deploy to a staging site by default, and to a live site if a parameter is given in order to stop things being deployed by mistake. Ideally use Codeship. Deploy to staging on a push to your develop branch and deploy to live on a merge to master. 
### How to rollback a failed deploy Any automated deploy process 

**must** be backed by an automated rollback proceedure that has been tested and is straightfoward to run. Automated deployments should test every stage as they deploy and bail out at the first sign something is wrong, rolling back any changes as they go. Further to that, a developer should be able to rollback a deployment easily Eg `gulp rollback live` 
## Backups Details of the backup process, locations of backups, process for loading a site from a backup. 

## SUPPORT