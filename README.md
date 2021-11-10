# Documentation Format

Documentation is required to be written in **pure text files** with **specific format**, so as to enforce uniformity, use auto-generation of HTML, and later application of themes throughout the documentation.

For easy management, supporting files can be kept with documentation. Thereby, auto-segregation of documentation files from others requires that documentation files be identified with file extension **.ubd** (for example: summary.ubd).

Files can be placed under any directory structure inside the same parent directory.

Only the described format will be enough to produce valid documentation pages.

Since, only **pure / plain text files** are required; Word Editors like _Microsoft Word_ and _Word-Pad_ are **not allowed** because they store text files in formatted binary / other formats. Following are a few examples of text editors that can be used for this purpose:

> * Notepad
> * [Notepad++](https://notepad-plus-plus.org/downloads/)
> * [VS Code](https://code.visualstudio.com/Download)
> * vim
> * gedit
> * nano
> * [Sublime Text](https://www.sublimetext.com/)



## Legibility Consideration

### White-space
For the purpose of this documentation, any combination of spaces (ASCII **32**) and tabs (ASCII **9**) are defined as white-space.

### Blank lines
Blank lines are hereby defined as lines without text, or having only white-spaces. Blank lines will be ignored in process of documentation generation, they are only to serve the purpose of legibility.

### Comments
Tilde (**~**) being first non-white-space letter on any line will make that line a comment; and line will be ignored in final output.



## Identifiers (IDs)

To provide late linking across files and sequencing content automatically, numeric identifiers are required to be placed in text files; **especially at the beginning of files**. Leading white-spaces as well as any number of white spaces before ID and Title are allowed as long as it's format is followed.

Each identifier, whenever & wherever placed, will mark beginning of a specific portion. Thereby, content can be distributed in separate files and later joined according to these identifiers. Numeric nature of these identifiers will allow automatic sorting, thereby _extreme care_ is required to avoid collissions amongst same types of identifiers under same levels of hierarchy - such collissions (if any) will produce unpredictable sequencing.

> **For example**, identifier **1** can be given to Minor sections which have different Major section identifiers but should not be given to Minor sections under same Major section.

Following identifiers are defined and their respective purpose is also mentioned (replace ID with number):


```
@Major ID Title
```

> Defines Major Group that contains one or many Minor Groups (with same Major ID).
> 
> It means that any content coming after this identifier (in current file) will be grouped with content that might be in some other file with same ID.
> 
> For standardization and to avoid collissions (as of now), following Major IDs are assigned:
> 
>> IDs **100000** till **199999** are reserved for **non-technical groups**
>> 
>> IDs **200000** till **299999** are reserved for **technical groups**
>
> **Title** should be used only once in all the files for same Major ID, otherwise it will be picked up from first non-blank occurrence.


```
@Minor ID Title
```

> Defines Minor Group that contains one or many Sections under same Minor ID.
> 
> This identifier is intended to group same kind of sections under a single ID, no matter the number of files they are scattered in.
>
> **Title** should be used only once in all the files for same Minor ID, otherwise it will be picked up from first non-blank occurrence.


```
@Section ID Title
```

> Defines Section that contains one or many Pages under same Section ID - a group of Pages.
>
> **Title** should be used only once in all the files for same Section ID, otherwise it will be picked up from first non-blank occurrence.


```
@Page ID Title
```

> Defines Page that contains content.
> 
> **Important!** One page should be completed in one file.
> 
> This identifier will allow sorting of pages in ascending order within a section.



## Content / Data Format


### Sections

Following format is allowed for formatting section start:

```
$H1 Section Heading
$H2 Section Sub-heading
$DT Section Description Text
$QT Motivational Quotation Text
$QB Motivational Quotation Author
$BG Section Background Image File - full path with extension (otherwise same directory will be used for full file name)
```

Section denoting symbol should be at the beginning of a line, otherwise, the section symbol will be ignored. However, white-spaces are allowed before section symbol.


### Headings

Following heading formats are allowed to define headings of various levels:

```
#H1  Heading Text - Biggest Heading
#H2  Heading Text
#H3  Heading Text
#H4  Heading Text
#H5  Heading Text
#H6  Heading Text - Smallest Heading
```

Headings denoting symbols should be at the beginning of any line, otherwise, they will be ignored. However, white-spaces are allowed before them.


### Paragraphs

**Para:** symbol at the beginning of any line will denote beginning of paragraph. Whereby, all subsequent lines will be joined into one paragraph till any other element's symbol or next paragraph symbol for segregation.


### Bold-faced Text

For making text bold-faced within paragraphs enclosed it within **Curly Braces** like **{text}**.

> For example:
> 
>> Para: This is a {bold-faced} text
> 
> will be displayed as
> 
>> This is a **bold-faced** text


### Italicized Text

For making text italicized within paragraphs enclose it within **Square Brackets** like **\[text\]**.

> For example:
> 
>> Para: This is an \[italicized\] text
> 
> will be displayed as
> 
>> This is an _italicized_ text


### Underlined Text

For making text underlined within paragraphs, start specific portion with an Underscore (**\_**) symbol and end underlining with the same symbol. Use **\_\_** (double Underscore) to insert an Underscore within text.


### Strike-through Text

For making text striked-through within paragraphs, start specific portion with a Hyphen (**-**) symbol and end cutting with the same symbol. Use **--** (double Hyphen) to insert a Hyphen within text.


### Images

To attach images, following format is required, at the beginning of any line:

```
%IM[Caption](full path with file extension)
```


### Links

There are two types of links allowed for documentation purposes. First is any URL (e.g., https://ubrant.com), and the second one is to point towards documentation parts. Hence following formats are supported (in second format, all elements are optional except TEXT and Annotation, but when present they should be in specified sequence separated with commas):

```
%L1[TEXT][Annotation](URL)
%L2[TEXT][Annotation](Major-ID, Minor-ID, Section-ID, Page-ID)
```

---

## End

It's not final format, more elements will be added upon requirement.

