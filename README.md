metadata-concepts
=================

This repository contains a listing of metadata values used in
[IKDP](https://github.com/langdoc/IKDP) and
[IKDP-2](https://github.com/langdoc/IKDP-2) language documentation
projects, and the values are mapped between CMDI, project’s internal
Filemaker Pro database, and the terms Niko Partanen attempts to use in
project’s more or less internal R scripts and functions.

The discussion about standards seem to circulate often around **the
format structure**, which in many ways is the least important, most
mechanical, part of the question. It is more important to think what
kind of data and values we have and need. It seems that these values
eventually are rather similar across projects, although the exact
implementation and structures would differ. Even more essentially, it
seems there is kind of a **core** for possible information, without
which the data is almost unusable to start with. It is essential to know
**where** something was done, **when** and **with who**, but then there
are details that are arguably less crucial. One way to think about this
is that there are some values we just have to have and can have for
every recording we work with, so there is some kind of a basic minimum
on which we can compare every item, but then there are attributes which
exclude some sessions as we don’t have sufficient metadata.

So more recording sessions we have to exclude from comparison because
the metadata field in question is lacking, more peripheral that field
has to be. Someone can argue it is super-important, but if nobody has
ever collected it, then it probably is not. Another example is that for
M.A. Castrén’s data (1844) we can’t really specify the participants or
locations, whereas for bit newer data such as that of Fokos-Fuchs’s
(1913) we generally can do that, up to a certain degree, so this sets
kind of a non-arbitrary boundary between these two datasets.

It is obvious that in different environments there are needs to call
things different. What would be in a presentation or on a website
`English title` is in database something like `title-en` and in R
dataframe `title_en`. All these refer to the same concept, and the idea
here is to map all these concepts and their variants to one another.
Similarly different concepts have to be mapped to their translations,
and ideally everything would be done in a manner where each piece of
information would be stored only once.

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 16%" />
<col style="width: 39%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Freiburg-Filemaker</th>
<th style="text-align: left;">Niko’s R Dataframe</th>
<th style="text-align: left;">CMDI</th>
<th style="text-align: left;">ELAN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Header/MdCreator</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Header/MdCreationDate</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Header/MdProfile</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">filename</td>
<td style="text-align: left;">ResourceProxy/ResourceRef</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">lat-session/History</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">Sessions::Session_name</td>
<td style="text-align: left;">session_name</td>
<td style="text-align: left;">lat-session/Name/</td>
<td style="text-align: left;">{filename}</td>
</tr>
<tr class="odd">
<td style="text-align: left;">Sessions::Title_eng</td>
<td style="text-align: left;">session_title</td>
<td style="text-align: left;">lat-session/Title</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_date</td>
<td style="text-align: left;">lat-session/Date</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_description</td>
<td style="text-align: left;">lat-session/descriptions/Description</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_continent</td>
<td style="text-align: left;">lat-session/Location/Continent</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_country</td>
<td style="text-align: left;">lat-session/Location/Country</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_address</td>
<td style="text-align: left;">lat-session/Location/Address</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_lat</td>
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">session_lon</td>
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">project_title</td>
<td style="text-align: left;">Project/Title</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">project_id</td>
<td style="text-align: left;">Project/Id</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Name</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Address</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Email</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/Contact/Organization</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Project/descriptions/Description</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">Sessions::Genre</td>
<td style="text-align: left;">genre</td>
<td style="text-align: left;">Content/Genre</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">subgenre</td>
<td style="text-align: left;">Content/Subgenre</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/Task</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/Modalities</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/Subject</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/Interactivity</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">Sessions::Session_arrangement_level</td>
<td style="text-align: left;">planning_level</td>
<td style="text-align: left;">Content/CommunicationContext/PlanningType</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/Involvement</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/SocialContext</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/EventStructure</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Content/CommunicationContext/Channel</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;">Actor_links::Role</td>
<td style="text-align: left;">participant_role</td>
<td style="text-align: left;">Actors/Actor/Role</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Actors/Actor/FullName</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;">Naming_convention</td>
<td style="text-align: left;">participant</td>
<td style="text-align: left;">Actors/Actor/Code</td>
<td style="text-align: left;"><a href="mailto:TIER/@PARTICIPANT">TIER/@PARTICIPANT</a></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Actors/Actor/FamilySocialRole</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;">Actors::Ethnicity</td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Actors/Actor/EthnicGroup</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">Actors::Birthtime_year</td>
<td style="text-align: left;">birthdate</td>
<td style="text-align: left;">Actors/Actor/Birthdate</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;">Actors::Sex</td>
<td style="text-align: left;">sex</td>
<td style="text-align: left;">Actors/Actor/Sex</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">Actors::Education</td>
<td style="text-align: left;">education</td>
<td style="text-align: left;">Actors/Actor/Education</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">age</td>
<td style="text-align: left;">Actors/Actor/Age</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/Type</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;">fileformat</td>
<td style="text-align: left;">Resources/MediaFile/Format</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/Size</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;">Sessions::Recording_quality</td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/Quality</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">Sessions::Recording_conditions</td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/RecordingConditions</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/TimePosition/Start</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/MediaFile/TimePosition/End</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Date</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Type</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Format</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Size</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Derivation</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/CharacterEncoding</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/ContentEncoding</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;">language</td>
<td style="text-align: left;">Resources/WrittenResource/LanguageId</td>
<td style="text-align: left;"><a href="mailto:TIER/@LANG_REF">TIER/@LANG_REF</a></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Anonymized</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Validation/Type</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Validation/Methodology</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Validation/Level</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Availability</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Date</td>
<td style="text-align: left;"></td>
</tr>
<tr class="odd">
<td style="text-align: left;"></td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Owner</td>
<td style="text-align: left;"></td>
</tr>
<tr class="even">
<td style="text-align: left;">OriginalPublication</td>
<td style="text-align: left;"></td>
<td style="text-align: left;">Resources/WrittenResource/Access/Publisher</td>
<td style="text-align: left;"></td>
</tr>
</tbody>
</table>

Tasks
-----

-   Setting up Travis CI to compile README.Rmd automatically
-   Add new values and mappings
-   There has to be some way to indicate that things like **session
    date** is actually stored only in the session name.
    -   For example, there are conventions such as session name has
        fields:
        `{language}_{variety}{year}{month}{date}{nth-recording of a day}`
    -   So session date value actually maps into `{year}{month}{date}`
        complex in the session name… Maybe not ideal, but if you have
        that value somewhere in the database, then you have to maintain
        two distinct values, and having it in filename just makes
        browsing files million times easier!
-   How one specifies that `age` is a calculated from birth time and
    session’s recording time?

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
