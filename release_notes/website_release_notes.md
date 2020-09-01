* reverse chronological order

* Source cod package release notes on GitHub are here: https://github.com/iedadata/EarthChemLibrary/releases

Public facing website release notes are here: [TBD]

#### January 2018

* Version ECL v3.5.0 release notes. Release date: Jan. 29, 2018

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


#### Novemember 2015

* Version 3.3 release notes (Nov. 6, 2015)

GRL-181, GRL-228 and GRL-232, GRL-222

1. Database schema enhancement: Add new table to keep geometry information. Modified an existing table schema to link IGSN with geometry information.

2. Several scripts are written to backfill all geometry and IGSNs information into database.

3. The script to automate uploading IGSNs and geometry information is implemented.

4. Map Search is implemented.

5. Bug fixes in search by IGSN.

#### July 2015

* Version 3.2 release notes (July 24, 2015)

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


#### January 2015

* Version 3.1 (expected deploy to dev on Jan 5, 2015)

    Inform user and ECL admin if file upload is not successful
    Align display of file names on admin view
    Improvement on autho/person search
    Align searches on public and admin interface
    Save session
    Fix chrome error during file download
    Clean up back end of dataset_file_list and co-author columns

#### November 2014

* Version 3.0

    Changes to backend, ECL source code moved to GitHub
    Synched production and development and GitHub
    Capability to display the link to an older or newer version from the Dataset Profile page
    Improvements to MyECL - links to edit profile, view submissions, and submit new data.
    Semi-automated DOI notification email (copy and paste)
    Semi-automated json file  (copy and paste)
    Added dynamically generated "How to Cite this Data" to each DCL dataset profile page
    Migrated EarthChemLibrary data to newer version of PostgreSQL server
    Backfilled original name into ECL

#### Feb-April 2014

* Version 2.5.2

    Fix static title in Thomson-Reuter xml.
    Add abstract and keywords tags in Thomson-Reuter xml.

* Version 2.5.1

    Add option to save Thomson-Reuter xml to file.

* Version 2.5.0

    Add multiple file replace functionality in admin tools.
    Add various messages/instructions in admin tools.
    Add editing functionality on DOI section of admin tool.
    Add file delete and file add functionality to admin tools.
    Add Thomson-Reuter xml file generation.
    Add citations section for detail submission record.

* Version 2.4.1

    Removed obsolete files.
    Update gitignore
    Make use of dynamic paths

#### October 2013

* Version 2.4.0

    Multiple file upload
    Multiple file download
    Search by datatype
    Browse by related synthesis database
    Enhanced author entry

Other things to remind users:

    Link to DOI
    Link to Award
