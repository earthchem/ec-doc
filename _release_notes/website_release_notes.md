   [![NSF-1948806](https://img.shields.io/badge/NSF-1928366-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1948806)

## EarthChem Library Repository - Release Notes

* Source code package release notes on GitHub are here: https://github.com/iedadata/EarthChemLibrary/releases


Version | Release Date
--------|-------------
[v 4.0.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-400)  | August 26, 2020
[v 3.6.9](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-369)  | April 27, 2020
[v 3.6.8](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-368)  | February 4, 2020
[v 3.6.7](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-367)  | September 23, 2019
[v 3.6.6](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-366)  | April 26, 2019
[v 3.6.5](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-365)  | April 12, 2019
[v 3.6.4](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-364)  | December 19, 2018
[v 3.6.3](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-363)  | August 10, 2018
[v 3.6.1, v 3.6.2](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#versions-361-and-362)  | July 13, 2018
[v 3.6.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-360)  | May 4, 2018
[v 3.5.1](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-351)  | March 20, 2018
[v 3.5.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-350)  | January 31, 2018
[v 3.4.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-340)  | November 8, 2017
[v 3.3.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-330)  | November 6, 2017
[v 3.2.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-320)  | July 24, 2015
[v 3.1.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-310)  | January 31, 2015
[v 3.0.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-300)  | November 21, 2014
[v 2.5.2](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-252)  | April 22, 2014
[v 2.5.1](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-251)  | February 21, 2014
[v 2.5.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-250)  | February 4, 2014
[v 2.4.1](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-241)  | October 25, 2013
[v 2.4.0](https://github.com/earthchem/ecl-doc/blob/master/release_notes/website_release_notes.md#version-240)  | October 4, 2013

#### Version 4.0.0
* August 2020
```
1. Implemented ORCID Login for contributors.

2. If a user updates their existing GEOPASS profile with ORCID ID, they can see all of their submissions and then login using ORCID.

3. ORCIDs can be added for Lead and Co-authors on the Submission Form.

4. User profile pages now support middle name, department, city, postal code and country information.

5. Implemented AstroMat Repository v 1.0.0 based on ECL v 4.0.0.

6. Improved layout for landing pages and submission form buttons.

7. Added DOIs to the Search Results page.

8. Added DataCite Metadata field IsPreviousVersionOf to DOI XML metadata.

9. Fixed a bug occurring when updating previously saved submissions.

10. Enhanced functionality for ECL REST API, to retrieve latest submissions to the ECL.
```

#### Version 3.6.9
* April 2020
```
1. Implemented a script for emailing ECL user survey

2. Updated text on FAQ page

3. Streamlined PHP script for DOI assignment, faster access to submission directory, and user download statistics.

4. Implemented log monitoring for components of website (Checklist, FAQ) to track usability statistics.
```
#### Version 3.6.8
* February 2020
```
1. After submitting data to the EarthChem Library users are invited to fill out a survey to help improve the functionality of the interface.

2. Users can check Frequently Asked Questions about data submissions.

3. When updating the publication DOI in MyECL, users will receive an email notification.

4. Related Publications and their DOIs are featured higher on ECL landing pages.

5. File uploading instructions have been updated.

6. Improved search capabilities for Clumped Isotope data type.
```
#### Version 3.6.7
* September 2019
```
1. Improved discoverability on Google search engine

2. Added zip, gz to allowed file format list

3. User contributed keywords are available on landing pages for published submissions

4. Multiple publication DOIs can be associated with a submission

5. Users can update their related publication DOI(s) on the myECL page after the dataset is submitted

6. Users will receive an automated email when the release date of their dataset is one month out (see http://www.earthchem.org/help/guidelines for more information about submission release dates)

7. Added functionality to download files from URLs for long term archive

8. Citation texts conform to ESIP standard across ECL
```
#### Version 3.6.6
* August 2019
```
1. Updated DOI registration feature to use the new version of DataCite's REST API.

2. Consolidated DOI and ECL landing pages and updated DOI landing page URLs to resolve to ECL landing pages.

3. Added Smithsonian volcano numbers to relevant past submissions and updated the DOI and metadata records of these submissions. 

4. Migrated pre-existing cruise DOIs and IGSNs into a consolidated related identifier table.

5. Added a confirmation message after successful dataset submissions. 

6. Improved clarity and number of metadata fields displayed on the ECL landing page.
```
#### Version 3.6.5
* April 2019
```
1. Users can now link their ECL datasets to related identifiers and information such as IGSN, Smithsonian Volcano Number, and Cruise DOI.

2. The ECL now offers REST APIs for these external identifiers and is working to expand these APIs in future releases.

3. ECL dataset landing pages now align more closely with DOI landing pages.

4. Users submitting to the ECL can now select if they would like to submit their dataset to be reviewed for inclusion in PetDB.

5. Users are now able to change the release date of their dataset after it has been submitted or published. The release date may not be set more than two years beyond the date metadata was published.

6. Improved handling of download statistics and summaries sent to users.

7. Improved the security of personal ECL record pages.
```
#### Version 3.6.4
* December 2018
```
1. Users can now choose the license they would like to associate with their dataset.

2. Improved handling of long-term archiving and bag creation. 

3. Fixed bugs related to saved submissions and large file sizes.

4. Improved clarity of error messages when the uploaded file size exceeds the limit.

5. Increased file name length. 

6. Funding source now propagates to DataCite for NASA and Other award types.

7. Improved the automation of download statistics sent to users so that the same user does not receive multiple reports.
```
#### Version 3.6.3
* August 2018
```
Several minor bug fixes.
```
#### Versions 3.6.1 and 3.6.2
* July 2018
```
Automated email notification to users with download statistics for their contributed datasets.

Added additional navigation features.

Several bug fixes.
```
#### Version 3.6.0
* May 2018 
```
1. Changed submission workflow to incorporate funding award number entry into the data submission web form, reducing potential barriers to submission.

2. ECL submission form now allows entry of multiple funding awards and funding sources (NSF, NASA, and Other).

3. Improved validation of NSF funding awards, using NSF web service, rather than internal harvest of award subset.

4. All datasets submitted to the ECL are now required to receive a DOI. This was previously suggested, but not required.

5. Updated disclaimer pop-up page upon dataset download to include clearer guidance on how to cite ECL datasets.

6. Improved the display of latitude and longitude in search by map.

7. Improved navigation upon logout from MyECL.

8. Styled ECL search, submit, browse, and MyECL pages to fit with new EarthChem website style.
```

#### Version 3.5.1
* March 2018 
```
   EarthChem Library dataset DOI records are now automatically converted to another metadata standard, known as ISO.

   Several small bug fixes.
```  

#### Version 3.5.0
*  January 2018 (Jan. 29, 2018)

Improvements:

    Upgraded ECL DOI XML records to DataCite schema V4.0.
        Added new fields to DOI XML records. Such as IGSN, GeoBoundingBox, GeoPoint, CreatedDate, etc. See details here .
        Changed DOI number generation method.
    Automated DOI XML record generation and registration process. See detail here .
    Added UI to generate email notification for quarterly data usage report.
    Automated download statistics plot.

New Feature:

    Implemented DOI XML record web service.

Database changes:

    Added new column 'dataset_doi_created' in submissions table.
    Added new ECL and IEDA related keyword tables and mapping table.
    Added new person external identifier table for ORCID etc.
    Added new cruise mapping table.
    Added new submission relationship table.
    Added XML feature for database.

#### Version 3.4.0
* November 2017
```
User download statistics, including email, IP address, and submission ID, tracked internally in the ECL database, rather than in an external system.
Restyled download disclaimer page.
```
#### Version 3.3.0

*  November 2015 (Nov. 6, 2015)
```
GRL-181, GRL-228 and GRL-232, GRL-222

1. Database schema enhancement: Add new table to keep geometry information. Modified an existing table schema to link IGSN with geometry information.

2. Several scripts are written to backfill all geometry and IGSNs information into database.

3. The script to automate uploading IGSNs and geometry information is implemented.

4. Map Search is implemented.

5. Bug fixes in search by IGSN.
```
#### Version 3.2.0

* July 2015 (July 24, 2015)

Bug Fixes:

    GRL-219, Align display of file names on admin view
    GRL-224, Add Published Lead Authors to drop down list for this quarter
    GRL-207, Fix error for file download in Admin that happens in the Chrome browser

Enhancements:

    GRL-206, Submission table clean up and new table status is created.
        lead_author, co_author, deleted, removed and approval columns are removed status_id column is added.
    GRL-214, Consolidate search.php and submission_search.php views.
        Aligned what the Admin search sees to be included in the public view search.
    GRL-223, Inform user and ECL admin if file upload is not successful.
        Added a Approval Status section in the usual email admin gets when a new submission is in ECL.
        A secondary email has been created to alert the admin. This is when there is a bigger issue usually on the connectivity of the user side.
        A tertiary email has been created to alert the admin. This is when there is issues with the external submission.
    GRL-218, Improvement to Author/Person search (James Gill example)
    GRL-209, Convert to Dynamic checkboxes
        Checkbox choices  pull from database
        Add new Data type SocialScience to the list
    GRL-238, Add version number to ecl pages browse, search, submit, user home and admin home.
    GRL-237, various DB changes for consolidation and cleanup.

New Functionality: 

     GRL-212, Add capability for users to save a session if they cannot complete a submission.
        Make a new status for the submission. 0 Incomplete , 1 Submitted, 2 Published , 3 Rejected , 4 Archived, 5 ExternalResource name the column as submissions.status_id.
        Enhance View My EarthChem Library Records page to include displaying all status 5 submissions which belongs to the person who is logging into geopass. Link will read "Continue Submission".
        Enhance the myECL home page to notify users to continue with their save and incomplete submission.
        Strip out queries in various views and construct classes for them. This will reduce duplicates for query calls.
        Prefill all form values from the saved session. Even for dynamic sections such as co authors and lead author from drop down or new lead author.
        Place checks for access to users on their own form. Trying to access other saved forms should be forbidden.
        Let users edit files before final submission. (reupdate)
        Admins do not need to be notified by email of a saved submission
        Cosmetic changes to the page "View MY ECL records" and main myECL Page
    GRL-228 Implement search by IGSN
        Add new table public.dataset_file_external_identifier.
        search includes new field for igsn number
            The igsn field is not required and no entry is made the search will continue without user prompts.
            Take in igsn number min range 9 to max range 10
            If a user enters a igsn less than 9 alphanumeric digits a error message prompts the user to fix the entry before search submission.
            If a user enters a igsn more than 10 alphanumeric digits a error message prompts the user to fix the entry before search submission.


#### Version 3.1.0
* January 2015  
```
    Inform user and ECL admin if file upload is not successful
    Align display of file names on admin view
    Improvement on autho/person search
    Align searches on public and admin interface
    Save session
    Fix chrome error during file download
    Clean up back end of dataset_file_list and co-author columns
```
#### Version 3.0.0
* November 2014
```
    Changes to backend, ECL source code moved to GitHub
    Synched production and development and GitHub
    Capability to display the link to an older or newer version from the Dataset Profile page
    Improvements to MyECL - links to edit profile, view submissions, and submit new data.
    Semi-automated DOI notification email (copy and paste)
    Semi-automated json file  (copy and paste)
    Added dynamically generated "How to Cite this Data" to each DCL dataset profile page
    Migrated EarthChemLibrary data to newer version of PostgreSQL server
    Backfilled original name into ECL
```

#### Version 2.5.2
* April 2014
```
    Fix static title in Thomson-Reuter xml.
    Add abstract and keywords tags in Thomson-Reuter xml.
```
#### Version 2.5.1
* Feb 2014
```
    Add option to save Thomson-Reuter xml to file.
```
#### Version 2.5.0
* Feb 2014
```
    Add multiple file replace functionality in admin tools.
    Add various messages/instructions in admin tools.
    Add editing functionality on DOI section of admin tool.
    Add file delete and file add functionality to admin tools.
    Add Thomson-Reuter xml file generation.
    Add citations section for detail submission record.
```

#### Version 2.4.1
* October 2013
```
    Removed obsolete files.
    Update gitignore
    Make use of dynamic paths
```
#### Version 2.4.0 
* October 2013
```
    Multiple file upload
    Multiple file download
    Search by datatype
    Browse by related synthesis database
    Enhanced author entry
```
Other things to remind users:

    Link to DOI
    Link to Award
