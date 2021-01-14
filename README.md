# decal-websites

This repo contains course website templates for Micromouse, HOPE, and Cybersecurity DeCals.

**Micromouse** - https://ieee.berkeley.edu/micromouse

**Hands-On PCB Engineering (HOPE)** - https://ieee.berkeley.edu/hope

**Cybersecurity** - https://ieee.berkeley.edu/cybersecurity

Websites are developed for the darkweb theme. See https://github.com/IEEEBerkeley/darkweb for the theme. Check the decal branch for the most recent decal-related development version.

Last updated: Jan 14th, 2021 (Spring '21)

## Preview



## Files

Raw HTML, CSS, and relevant Handlebars files are included in this repo. Previous versions saved under each semester's folder name.

See **instructions** on how to deploy it on Ghost.

## Instructions

This section contains instructions for 4 different cases as follows:

a. Deploying HTML to Ghost

b. Deploying CSS to Ghost (theme embed)

c. Deploying CSS to Ghost (editor)

d. Setting up a new semester's website (when the semester ends and the current website has to be archived)

**Deploying HTML on Ghost**

0. Access the Ghost editor through ieee.berkeley.edu/ghost.
1. Copy the HTML section in *yourdecalname.html* (from body to /body).
2. Paste the selection into the Ghost editor. The page is named yourdecalname (semester). You can search your decal's website by filtering through tags.
3. Save the editor and make sure it is published under the domain of ieee.berkeley.edu/*yourdecalname*.
4. Now it's time to deploy the CSS on Ghost!

**Deploying CSS on Ghost (theme embed)**

The current darkweb theme in IEEEBerkeley/darkweb should already have the theme embedded, but just in case here it goes:

1. Save decalwebsite.css into darkweb/assets/css
2. Import the CSS by adding a <link rel="stylesheet" type="text/css" href="{{asset 'css/decalwebsite.css'}}"> to the first block of the Ghost editor.

**Deploying CSS on Ghost (editor)**

If the CSS is already theme embedded, don't worry about this part.

1. Paste the CSS contents in *yourdecalname.html* into the first block of the Ghost editor (from <style> to </style>).

**Setting up a new semester's website**

It is recommended to contact a website team for this but the steps are as following:

1. Git clone IEEEBerkeley/darkweb onto your local computer
2. Create a new file called *page-yourdecalname-currentsemester.hbs* (example: page-micromouse-fa20.hbs)
3. Make sure the contents of your new file is identical to *page-yourdecalname.hbs*
4. Compress the theme using ```npm run zip``` inside the src directory (see IEEEBerkeley/darkweb instructions)
5. Upload the theme on ghost under the designs tab
6. Open the Ghost page editor and change the published URL to *yourdecalname-currentsemester*
7. Make a copy of the current page and publish the page under *yourdecalname*
8. Done! You have successfully archived a previous version of the website and created a new version of the website! Edit the contents of the website accordingly and you are all set.

## Troubleshooting / FAQ

**The header/footer breaks on my DeCal's website**

This is probably due to CSS conflicts. If the theme's CSS classes and decalwebsite CSS collide with each other (same name), the header/footer inherits the decalwebsite CSS as the priority. Make sure to check if you have added any external stylesheets or scripts that cause such collisions.

**My DeCal's website looks too wide**

This is due to *page-yourdecalname.hbs* inheriting an old version of the theme. You can edit decalDefault.hbs to set the page width.

**If all else fails**

Contact John Lee through Slack and I will come help :)
