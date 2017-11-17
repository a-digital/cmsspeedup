# CMS Speed Up plugin for Craft CMS

Performs a CMS Speed Up after an update is completed.

## Installation

To install CMS Speed Up, follow these steps:

1. Download & unzip the file and place the `cmsspeedup` directory into your `craft/plugins` directory
2.  -OR- do a `git clone ???` directly into your `craft/plugins` folder.  You can then update it with `git pull`
3. Install plugin in the Craft Control Panel under Settings > Plugins
4. The plugin folder should be named `cmsspeedup` for Craft to see it.  GitHub recently started appending `-master` (the branch name) to the name of the folder for zip file downloads.

CMS Speed Up works on Craft 2.4.x, Craft 2.5.x and Craft 2.6.x.

## CMS Speed Up Overview

This plugin has been built to follow the recommendations made in https://zacharyflower.com/tutorials/2017/02/27/speed-up-craft-admin.html and also address the issue of what happens after the cms is updated.

It copies our craft/app/resources folder into public/{{ cpTrigger }}/resources so that requests for these files can find their target without having to be processed by craft.

## Configuring CMS Speed Up

There are no settings for this plugin, it is just a simple install.

We have however experienced a redirection issue with the cpTrigger on some occasions and had to add the following rule to our .htaccess file under the public directory to resolve this:

`RewriteRule ^{cpTrigger}$ https://{domain.com}/{cpTrigger}/login [R=301,L,NC]`

If you experience this issue then the change to your .htaccess file should also fix this for you.

## Using CMS Speed Up

You don't need to do anything as it just copies files which speeds up our control panel resource requests.
If you experience redirection issues on the base cp url then there is a fix that we have found described above.

## CMS Speed Up Changelog

### 1.0.0 -- 2017.11.16

* Initial release

Brought to you by [Matt Shearing](adigital.agency)