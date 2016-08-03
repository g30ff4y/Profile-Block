# Profile-Block
A block for making profiles in the UMT Ponderosa Template in the Cascade CMS. The Profile Block has been an adaptation of a similar profile system developed by UM's Central IT Web Team, which was inherited by SFD on a collaborative site in 2013. I have since been maintaining and modifying the block to better serve SFD sites in the College of Humanities and Sciences. The following was originally documented with Bitbucket markdown intended for internal use and is provided here for reference.

Updated 5/27/16 @g30ff4y

[TOC]

##Overview
The Profiles Block allows for display of people that are not in the Employee Database, like undergraduate students and community volunteers. The Profiles block lists all people on a single page and can get lengthy. If you need to display many people not in the Employee Database in a slightly more condensed format like accordions, check to see if the project would work with the Roster System.
###Examples
* [IRSE](http://www.umt.edu/grad/irse/people/default.php)
* [Writing at Work Conference Panelists](http://hs.umt.edu/creativewriting/writing-at-work/participants.php)
* [MCLL Language Day Community Presenters](http://hs.umt.edu/mcll/language-day/ld-faculty.php)
* [Minds Lab Research Assistants](http://hs.umt.edu/_staging/severson/people/students.php)

##Implementation
###Connecting the Block
1. Browse to the starter block: SFD - New Templates > Blocks > blankSiteBlocks > Profiles Block
2. Select **Copy** from the fly-out menu to the right of the file name.
     1. Rename the block in the **System Name** line
     2. Select a new **Parent Folder** in the site you are working on.
     3. Click **Submit**. You will be automatically be taken to your new site.
3. Go to the page you need the profiles on.
     1. Click the **Edit** tab.
     2. Click **Outputs** in the blue bar below the Edit Tab.
     3. Select where you want the profiles to appear on the page; either above or below the main page content.  This will most likely be in either **DEFAULT-AFTER** or **DEFAULT-BEFORE** System Regions:
          1. **BLOCK:** Search for the profiles block you just copied.
          2. **FORMAT:** Search, then **Browse** to SFD - New Templates > scripts > Block Scripts > sfdBlockScripts > Profiles Block
###Adding Profiles
1. Edit the block you just connected.
2. You have the option to add groups of profiles and/or individual profiles in a group, each being infinite.  Use the standard Cascade Plus and Minus signs to add/delete either Groups or Profiles. Groups can be reordered with the black up and down arrows next to the add/delete options.
3. Groups have an option for a Heading.  Use the **Group Heading** line. This text will be formatted as a Heading Level determined by the Initial Heading Level selector in the Block Setup section.
4. Profiles can be reordered with the black up and down arrows next to the add/delete options. Each profile will have these fields to enter:
     1. **Title and/or Department:** This is a person's Tile or their Department which is rendered after the person's name.
     2. **First Name:** Person's first name.
     3. **Last Name:** Person's last name.
     4. **Link:** The link will wrap the person's first and last name with the Title/Department line. The link can be either internal (part of the current site) or a separate external site:
          1. **Internal Link:** Click search to browse to the page on the site to link to.
          2. **External Link:** Type specific url here, include http://
     5. **Email:** The person's email address. This will be rendered as it's own row.
     6. **Line:** Individual text lines
          1. Lines can only handle text, do not use any special characters.
          2. Up to six lines can be added and reordered with the black up and down arrows next to the add/delete options.
     7. **Image:** Add an image to the button.  Search for the image (must already be uploaded to the site)
     8. **Biography:** Use this area to add additional information.  Use the WYSIWYG editor to format information.  Will wrap image if no Lines are used.
##Setup
###Block Setup
* **Custom Block ID:**  Use this ID if you are using multiple profile blocks on a site and need them to behave differently based on custom css.
* **Initial Heading Level:**  Use this selector to set the Heading level of the **Group Heading** field.  Profile name and title fields will follow one level below this selected heading.
##Customizing
Follow the structure outlined in the Anatomy of a Profile to determine where the element you are targeting is located.  Each element has it's own class to target.  Additionally, when used with the Custom ID field, you can implement multiple instances of the Profile Block on a site with different styling.
###Anatomy of a Profile
```
#!html

<div id="custom-ID" class="remainder-box normal_page component">
     <div class="profile-group">
          <div class="block-heading">
               <h2>Block Heading</h2>
          </div>
          <div class="row-fluid profile">
               <a target="_blank" href="URL-Link">
                    <h3>First Last - Title</h3>
               </a>
               <div class="row-fluid profile-details">
                    <div class="col-xs-12 col-sm-4 profile_photo">
                         <img src="image.extenstion">
                    </div>
                    <div class="profile_info">
                         <div class="col-xs-12 col-sm-8 profile-email">
                              <p>
                                   <b>Email:</b><a target="_blank" href="mailto:email@domain.extension">email@domain.extension</a>
                              </p>
                         </div>
                         <div class="col-xs-12 col-sm-8 profile-lines">
                              <div class="row">
                                   <div class="col-xs-12 col-sm-6">
                                        <p>Line 1</p>
                                        <p>Line 3</p>
                                        <p>Line 5</p>
                                   </div>
                                   <div class="col-xs-12 col-sm-6">
                                        <p>Line 2</p>
                                        <p>Line 4</p>
                                        <p>Line 6</p>
                                   </div>
                              </div>
                         </div>
                         <div class="profile_bio">
                              <p>Biography Paragraph</p> 
                         </div>
                    </div>
               </div>
               <div class="profile_hr">
                    <hr>
               </div>
          </div>
     </div>
</div>

```

