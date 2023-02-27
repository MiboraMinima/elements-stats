# (PART) Notions de statistiques élémentaires {-}

# Les différents type de variables

[*https://statsandr.com/blog/variable-types-and-examples/*](https://statsandr.com/blog/variable-types-and-examples/){.uri}

Il existe 2 grandes catégories de variables : les **quantitatives**
(continues et discrètes) et les **qualitatives** (nominal et ordinal)
(fig. [1.1](#type_var){reference-type="ref" reference="type_var"}) ![Les
différents type de variables](figures/Variables_Types.png){#type_var
width="\\linewidth"}

## Quantitative

A quantitative variable is a variable that reflects a notion of
magnitude, that is, if the values it can take are numbers. A
quantitative variable represents thus a measure and is numerical.

Quantitative variables are divided into two types: discrete and
continuous. The difference is explained in the following two sections.

### Quantitative discrète

Quantitative **discrete** variables are variables for which the values
it can take are countable and have a **finite number of possibilities**.
The values are often (but not always) integers.

-   Number of children per family

-   Number of students in a class

-   Number of citizens of a country

Even if it would take a long time to count the citizens of a large
country, it is still technically doable. Moreover, for all examples, the
number of possibilities is finite. Whatever the number of children in a
family, it will never be 3.58 or 7.912 so the number of possibilities is
a finite number and thus countable.

### Quantitative continue

On the other hand, quantitative continuous variables are variables for
which the values are not countable and have an infinite number of
possibilities. For example:

-   Weight

-   Height

For simplicity, we usually referred to years, kilograms (or pounds) and
centimeters (or feet and inches) for age, weight and height
respectively. However, a 28-year-old man could actually be 28 years, 7
months, 16 days, 3 hours, 4 minutes, 5 seconds, 31 milliseconds, 9
nanoseconds old.

For all measurements, we usually stop at a standard level of
granularity, but nothing (except our measurement tools) prevents us from
going deeper, leading to an infinite number of potential values. The
fact that the values can take an infinite number of possibilities makes
it uncountable.

## Qualitative

In opposition to quantitative variables, qualitative variables (also
referred as categorical variables or factors in R) are variables that
are not numerical and which values fits into categories.

In other words, a qualitative variable is a variable which takes as its
values modalities, categories or even levels, in contrast to
quantitative variables which measure a quantity on each individual.

Qualitative variables are divided into two types: nominal and ordinal.

### Nominal

A qualitative **nominal variable** is a qualitative variable where **no
ordering is possible or implied in the levels**. For example, the
variable gender is nominal because there is no order in the levels
female/male. Eye color is another example of a nominal variable because
there is no order among blue, brown or green eyes.

A nominal variable can have between two levels (e.g., do you smoke?
Yes/No or what is your gender? Female/Male) and a large number of levels
(what is your college major? Each major is a level in that case).

### Ordinale

On the other hand, a qualitative **ordinal variable** is a qualitative
variable with an **order implied in the levels**. For instance, if the
severity of road accidents has been measured on a scale such as light,
moderate and fatal accidents, this variable is a qualitative ordinal
variable because there is a clear order in the levels.

Another good example is health, which can take values such as poor,
reasonable, good, or excellent. Again, there is clear order in these
levels so health is in this case a qualitative ordinal variable.


