# Document Format

Documentation is required to be generated in "pure" text files. So as to bring about uniformity, auto generation of documentation, and later application of themes throughout the documentation. Files with extension "**.ubd**" can be placed under any directory structure (with same parent directory). Only the described format will be desired to produce valid documentation pages. Therefore, Word Editors like Microsoft Word and Wordpad, that generate formatted binary / formatted files are not allowed. Following are a few examples of text editors that can be used for this purpose:

> * Notepad
> * Notepad++
> * VS Code
> * vim
> * gedit
> * nano
> * Sublime Text

---
---

## Legibility Consideration

**White-space**: For the purpose of this documentation, any combination of spaces (ASCII **32**) and tabs (ASCII **9**) are defined as white-space.

**Blank lines**: Blank lines are defined as text lines having zero or more white-spaces only. Blank lines will be ignored for the purpose of documentation generation, they are here only to serve the purpose of legibility.

**Comments**: Lines starting with Tilde (**~**) will be regarded as blank lines, as Tilde being first non-white-space letter will make any line a comment and will be ignored in final output.

## Identifiers

To achieve late linking across files and content sequencing, numeric identifiers are required to be placed in text files (especially at the beginning of file). These identifiers have to be placed at beginning of lines (leading white-spaces are allowed).

Each identifier, whenever & wherever placed, will mark beginning of a specific portion. Thereby, content can be distributed in separate files and later joined according to these identifiers. Numeric nature of these identifiers will allow automatic sorting of content, thereby _extreme care_ should be taken to avoid collissions amongst same types of identifiers under same levels, because such collissions will produce unpredictable sequencing.

> **For example**, identifier **1** can be given to Minor sections which have different Major section identifiers but should not be given to Minor sections under same Major section.

Following identifiers are defined and their respective purpose is also mentioned (replace ID with number):
        
        @Major ID Title
        
> Defines Major Group that contains one or many Minor Groups (with same Major ID).
> 
> It means that any content coming after this identifier (in current file) has to be grouped with content that might be in some other file but having same ID.
> 
> **Title** should be used only once in all the files, otherwise it will be picked up from first occurrence.
> 
> For standardization and to avoid collission (as of now), following Major IDs are assigned:
>> IDs **100000** till **199999** are assigned to **non-technical group**
>> 
>> IDs **200000** till **299999** are assigned to **technical group**
        
        @Minor ID Title
        
> Defines Minor Group that contains one or many Sections under same Minor ID.
> 
> This identifier is intended to group same kind of sections under a single group, no matter the number of files they are scattered in.
        
        @Section ID Title
        
> Defines Section that contains one or many Pages under same Section ID.
        
        @Page ID Title
        
> Defines Page that contains content.
> 
> **Important!** One page should be completed in one file.
> 
> This identifier will allow sorting of pages in ascending order.

---
---

## Content / Data

**Sections**: Following format is required to be used for forming section start:
        
        $1  Section Heading
        $2  Section Sub-heading
        $B  Section Background (Image file - full path with extension)
        
Section denoting symbol should be at the beginning of a line, otherwise, the section symbol will be ignored. However, white-spaces are allowed before section sybmol.

**Headings**: Following heading formats are required being used for headings of various levels:
        
        #1  Heading Level 1 (Biggest)
        #2  Heading Level 2
        #3  Heading Level 3
        #4  Heading Level 4
        #5  Heading Level 5
        #6  Heading Level 6 (Smallest)
        
Headings denoting symbols should be at the beginning of any line, otherwise, they will be ignored. However, white-spaces are allowed before them.

**Paragraphs**: Colon (**:**) symbol at the beginning of any line will denote start of paragraph. Whereby, all subsequent lines will be joined into one paragraph till the availability of any other element's symbol or next paragraph symbol for segregation.

**Bold-faced Text**: For making text bold-faced within paragraphs, start specific portion with an Aesterisk (**\***) symbol and end bold with the same symbol. Use **\*\*** to insert an Aesterisk in text.

**Italicized Text**: For making text italicized within paragraphs, start specific portion with a Forward Slash (**/**) symbol and end italicizing with the same symbol. Use **//** to insert a Forward Slash in text.

**Underlined Text**: For making text underlined within paragraphs, start specific portion with an Underscore (**\_**) symbol and end underlining with the same symbol. Use **\_\_** (double Underscore) to insert an Underscore within text.

**Strike-through Text**: For making text striked-through within paragraphs, start specific portion with a Hyphen (**-**) symbol and end cutting with the same symbol. Use **--** (double Hyphen) to insert a Hyphen within text.

**Images**: In order to attach images, following format is required, at the beginning of any line:
        
        %IM[Caption](full path with file extension)(Alternate text)
        
**Links**: There are two types of links allowed for documentation purposes. First is any URL (e.g., https://ubrant.com), and the second one is to point towards documentation parts. Hence following formats are supported (in second format, all elements are optional except TEXT, but when present they should be in specified sequence separated with commas):
        
        %L1[TEXT](URL)
        %L2[TEXT](Major-ID, Minor-ID, Section-ID, Page-ID)
        
---
---

## End

It's not final format, more elements will be added upon requirement.

