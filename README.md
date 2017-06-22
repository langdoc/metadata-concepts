# metadata-concepts

I'm not a big fan of standardization attempts when it comes to formats, as this often leads to endless discussion about **the format structure**, which in many ways is the least important, most mechanical, part of the question. It is more important to think about the data and in generally what kind of values we have. It seems that these values eventually are rather similar across projects, although the exact implementation and structures would differ. Even more essentially, it seems there is kind of a **core** for possible information, without which the data is almost unusable to start with.

This repository contains a listing of metadata values used in IKDP and IKDP-2 language documentation projects, and the values are mapped to IMDI, CMDI and project internal mysql database. There will also be scripts and stylesheets to shuffle these across one another.

It is obvious that in different environments there are needs to call things different. What would be in a presentation `English title` is in database `title-en` and in R dataframe `title_en`. All these refer to the same concept, and the idea here is to map all these concepts and their variants to one another. Similarly different concepts have to be mapped to their translations, and ideally everything would be done in a manner where each piece of information would be stored only once.

When one thinks about relations such as these, storing information relartions into a graph comes fast to mind as one alternative. In other projects, mainly in INEL, graph database has been used as data storage mechanism. This is probably a very good idea. In our model the use of graph structure is mode modest, and just used as one possible representation.

So very central idea here is that the same data is represented in CMDI XML, mysql database and graph database, and there is a seamless connection between these. What we need is the ability to access values themselves, and for this it should be irrelevant where they are stored.

Table below created with Dmitriy Levchenko.

- participant
    - participant-id
    - participant-name
        - type: first, middle, patronym, last
        - language: kpv, rus
    - participant-place
        - type: birth, current, stayed
        - period: start time, end time
    - participant-photo
    - participant-gender
- session
    - Id
        - location
    - time
        - period: start time, end time
    - tematika
    - title
        - language: kpv, rus, eng
    - status
    - filename
    - comment
        - language: kpv, rus, eng
    - project
    - source
    - description
        - language: kpv, rus, eng
    - language
- connection
    - Id informant
    - Id zaps
    - Rol
- location
    - id
    - name
        - language: kpv, rus
    - lat
    - lon

As a relational database, same structure, approximately, can be expressed like this:

- Информанты
    - Id
    - Name
    - Family
    - Otchestvo
    - God
    - Mesto rojdeniya id
    - Mesto jitelstva id
    - Foto
    - Pol
- Записи
    - Id
    - Mesto zapisi id
    - Time
    - Tematika
    - Title-ru
    - Title-en
    - Status (готовый и т.д.)
    - Nazvanie faila
    - Comments
    - Project
    - Istochnik
    - Description
- Связи
    - Id informant
    - Id zaps
    - Rol
- Место
    - Id
    - Nazvanie ru
    - Nazvanie kv
    - Coordinaty
