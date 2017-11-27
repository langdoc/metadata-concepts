metadata-concepts
=================

I’m not a big fan of standardization attempts when it comes to formats,
as this often leads to endless discussion about **the format
structure**, which in many ways is the least important, most mechanical,
part of the question. It is more important to think about the data and
in generally what kind of values we have. It seems that these values
eventually are rather similar across projects, although the exact
implementation and structures would differ. Even more essentially, it
seems there is kind of a **core** for possible information, without
which the data is almost unusable to start with.

This repository contains a listing of metadata values used in IKDP and
IKDP-2 language documentation projects, and the values are mapped to
IMDI, CMDI and project internal mysql database. There will also be
scripts and stylesheets to shuffle these across one another.

It is obvious that in different environments there are needs to call
things different. What would be in a presentation `English title` is in
database `title-en` and in R dataframe `title_en`. All these refer to
the same concept, and the idea here is to map all these concepts and
their variants to one another. Similarly different concepts have to be
mapped to their translations, and ideally everything would be done in a
manner where each piece of information would be stored only once.

So very central idea here is that whether same data is represented in
CMDI XML, mysql database or graph database is irrelevant, as there
should be a seamless connection between these. What we need is the
ability to access values themselves, and for this it not be that
important where they are stored.

<table>
<thead>
<tr class="header">
<th style="text-align: left;">Freiburg-Filemaker</th>
<th style="text-align: left;">Niko’s R Dataframe</th>
<th style="text-align: left;">CMDI</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Header/MdCreator</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Header/MdCreationDate</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Header/MdProfile</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">filename</td>
<td style="text-align: left;">ResourceProxy/ResourceRef</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">lat-session/History</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_name</td>
<td style="text-align: left;">lat-session/Name</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_title</td>
<td style="text-align: left;">lat-session/Title</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_date</td>
<td style="text-align: left;">lat-session/Date</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_description</td>
<td style="text-align: left;">lat-session/descriptions/Description</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_continent</td>
<td style="text-align: left;">lat-session/Location/Continent</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_country</td>
<td style="text-align: left;">lat-session/Location/Country</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_address</td>
<td style="text-align: left;">lat-session/Location/Address</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_lat</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_lon</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">project_title</td>
<td style="text-align: left;">Project/Title</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">project_id</td>
<td style="text-align: left;">Project/Id</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Name</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Address</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Email</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Organization</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/descriptions/Description</td>
</tr>
<tr class="even">
<td style="text-align: left;">genre</td>
<td style="text-align: left;">genre</td>
<td style="text-align: left;">Content/Genre</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">subgenre</td>
<td style="text-align: left;">Content/Subgenre</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/Task</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/Modalities</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/Subject</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/Interactivity</td>
</tr>
<tr class="even">
<td style="text-align: left;">planning_level</td>
<td style="text-align: left;">planning_level</td>
<td style="text-align: left;">Content/CommunicationContext/PlanningType</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/Involvement</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/SocialContext</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/EventStructure</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/Channel</td>
</tr>
<tr class="odd">
<td style="text-align: left;">Role</td>
<td style="text-align: left;">participant_role</td>
<td style="text-align: left;">Actors/Actor/Role</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Actors/Actor/FullName</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">participant</td>
<td style="text-align: left;">Actors/Actor/Code</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Actors/Actor/FamilySocialRole</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Actors/Actor/EthnicGroup</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">birthdate</td>
<td style="text-align: left;">Actors/Actor/Birthdate</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">sex</td>
<td style="text-align: left;">Actors/Actor/Sex</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">education</td>
<td style="text-align: left;">Actors/Actor/Education</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">age</td>
<td style="text-align: left;">Actors/Actor/Age</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/Type</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">fileformat</td>
<td style="text-align: left;">Resources/MediaFile/Format</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/Size</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/Quality</td>
</tr>
<tr class="even">
<td style="text-align: left;">RecordingConditions</td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/RecordingConditions</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">time_end</td>
<td style="text-align: left;">Resources/MediaFile/TimePosition/Start</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">time_start</td>
<td style="text-align: left;">Resources/MediaFile/TimePosition/End</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Date</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Type</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Format</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Size</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Derivation</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/CharacterEncoding</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/ContentEncoding</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">language</td>
<td style="text-align: left;">Resources/WrittenResource/LanguageId</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Anonymized</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Validation/Type</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Validation/Methodology</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Validation/Level</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Availability</td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Date</td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Owner</td>
</tr>
<tr class="even">
<td style="text-align: left;">OriginalPublication</td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Publisher</td>
</tr>
</tbody>
</table>

Tasks
-----

-   Setting up Travis CI to compile README.Rmd automatically
-   Add new values and mappings

Notes about fields to be added
------------------------------

Table below created with Dmitriy Levchenko. It mainly contains fields we
need to get into our system in Syktyvkar.

-   participant
    -   participant-id
    -   participant-name
        -   type: first, middle, patronym, last
        -   language: kpv, rus
    -   participant-place
        -   type: birth, current, stayed
        -   period: start time, end time
    -   participant-photo
    -   participant-gender
-   session
    -   Id
        -   location
    -   time
        -   period: start time, end time
    -   tematika
    -   title
        -   language: kpv, rus, eng
    -   status
    -   filename
    -   comment
        -   language: kpv, rus, eng
    -   project
    -   source
    -   description
        -   language: kpv, rus, eng
    -   language
-   connection
    -   Id informant
    -   Id zaps
    -   Rol
-   location
    -   id
    -   name
        -   language: kpv, rus
    -   lat
    -   lon

As a relational database, same structure, approximately, can be
expressed like this:

-   Participants
    -   Id
    -   Name
    -   Family
    -   Patronym
    -   Year
    -   Birthplace id
    -   Place of residence id
    -   Picture (id?)
    -   Gender
-   Session
    -   Id
    -   Recording place id
    -   Time
    -   Topics
    -   Title-ru
    -   Title-en
    -   Status (segmented, transcribed etc.)
    -   Session name
    -   Comments
    -   Project
    -   Source (published somewhere etc.)
    -   Description
-   Connections
    -   Id participant
    -   Id session
    -   Role
-   Places
    -   Id
    -   Name rus
    -   Name kpv
    -   Coordinates
