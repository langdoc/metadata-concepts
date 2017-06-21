# metadata-concepts

I'm not a big fan of standardization attempts when it comes to formats, as this often leads to endless discussion about **the format structure**, which in many ways is the least important, most mechanical, part of the question. It is more important to think about the data and in generally what kind of values we have. It seems that these values eventually are rather similar across projects, although the exact implementation and structures would differ. Even more essentially, it seems there is kind of a **core** for possible information, without which the data is almost unusable to start with.

This repository contains a listing of metadata values used in IKDP and IKDP-2 language documentation projects, and the values are mapped to IMDI, CMDI and project internal mysql database.

It is obvious that in different environments there are needs to call things different. What would be in a presentation `English title` is in database `title-en` and in R dataframe `title_en`. All these refer to the same concept, and the idea here is to map all these concepts and their variants to one another.

Table below created with Dmitriy Levchenko.

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
