# Documentation Format

The documentation in this format (***UBD***) is required being written in **pure text files** with **special text elements**, so as to enforce uniformity, automatically generating HTML, and later application of themes throughout the scope of documentation.

For easy management, supporting files can be kept with documentation. Thereby, auto-segregation of documentation files from others requires that documentation files be identified with ***.ubd*** extension (for example: *summary.ubd*).

Files can be placed under any directory structure inside single parent directory.

Following described format is deemed enough (for now) to produce valid documentation pages. Efforts shall be made that further improvements in format should not disrupt existing documentation.

Since, only **pure / plain text files** are required; Word Editors like _Microsoft Word_ and _Word-Pad_ are **not allowed** because they store text files in formatted binary / other formats. Following are a few examples of text editors that can be used for this purpose:

> * Notepad - Available in Windows
> * [Notepad++](https://notepad-plus-plus.org/downloads/)
> * [VS Code](https://code.visualstudio.com/Download)
> * vim - Available in Linux distros
> * gedit - Available in Linux distros
> * nano - Available in Linux distros
> * [Sublime Text](https://www.sublimetext.com/)





---





## Legibility Consideration

### White-space
For the purpose of this documentation, any combination of spaces (ASCII **32**) and tabs (ASCII **9**) are defined as white-space.

### Blank lines
Blank lines are hereby defined as lines without text, or having only white-spaces. Blank lines will be ignored in process of documentation generation, they are only to serve the purpose of legibility.

### Comments
Tilde (**~**) being first non-white-space letter on any line will make that line a comment; and line will be ignored in final output.





---





## Identifiers (IDs)

To provide late linking across files and auto-sequencing of content, numeric identifiers (**whole numbers**) are required to be placed **at the beginning of files**. Leading white-spaces as well as any number of white spaces before ID and Title are allowed as long as specific order is maintained.

>> **Note:** Items (majors, minors, sections and pages) with negative identifiers will be filtered-out during output generation

Each identifier, whenever & wherever placed, will mark beginning of that portion. Thereby, content can be distributed in separate files and later joined according to these identifiers. Numeric nature of these identifiers will allow automatic sorting, thereby _extreme care_ is required to avoid collissions amongst same types of identifiers under same levels of hierarchy - such collissions (if any) will produce unpredictable sequencing.

>> **For example**, identifier **1** can be given to Minor sections which have different Major section identifiers but should not be given to Minor sections under same Major section

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
>> IDs ***100000*** ➠ ***199999*** are reserved for ***non-technical*** groups
>> 
>> IDs ***200000*** ➠ ***299999*** are reserved for ***technical*** groups
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





---





## Content / Data Format


### Sections

Following format is allowed for formatting section start:

```
$H1: Section Heading
$H2: Section Sub-heading
$DT: Section Description Text
$QT: Motivational Quotation Text
$QB: Motivational Quotation Author
$BG: Section Background Image File - full path with extension
```

>> If full path to image file is not provided (i.e., only file name with extension is provided) then directory of documentation file will be used for picking-up the image

Section denoting symbol should be at the beginning of a line, otherwise, the section symbol will be ignored. However, white-spaces are allowed before section symbol.


### Headings

Following heading formats are allowed to define headings of various levels:

```
#H1: Heading Text - Biggest Heading
#H2: Heading Text
#H3: Heading Text
#H4: Heading Text
#H5: Heading Text
#H6: Heading Text - Smallest Heading
```

Headings denoting symbols should be at the beginning of any line, otherwise, they will be ignored. However, white-spaces are allowed before them.


### Paragraphs and Lists

"**#Para:**" at beginning of any line will denote starting a paragraph. Whereby, all subsequent lines will be joined into one paragraph till any other element's symbol or next paragraph symbol for segregation.

> For example:
> 
>> #Para: This is some paragraph text
> 
> will be displayed as
> 
>> This is some paragraph text

"**#List:**" at beginning of any line will denote starting an unordered list. Whereby, all subsequent lines will be joined into one unordered list till any other element's symbol or next list symbol.

> For example:
> 
>> #List:
>> 
>> List Item A
>> 
>> List Item B
>> 
>> List Item C
> 
> will be displayed as
> 
>> * List Item A
>> 
>> * List Item B
>> 
>> * List Item C


#### Bold-faced Text

For making text bold-faced within paragraphs and lists enclose it within **Curly Braces** and **B / b** like **{B text}**.

> For example:
> 
>> #Para: This is some {B bold-faced} text
> 
> will be displayed as
> 
>> This is some **bold-faced** text


#### Italicized Text

For making text italicized within paragraphs and lists enclose it between **Curly Braces** and **I / i** like **{I text}**.

> For example:
> 
>> #Para: This is some {I italicized} text
> 
> will be displayed as
> 
>> This is some _italicized_ text


### Images

To attach images, following format is required, at beginning of any line:

```
#Image: [Caption Text](full path with file name and extension)
```

>> When only image file name with extension is provided then same directory as documentation file will be used for picking-up the image


### Links

There are two types of links allowed in documentation:

* First type of links is full URL (e.g., https://ubrant.com); and
* The second one is intended to point towards documentation parts

Hence following formats are supported (inside text elements):

```
:Link-URL:[TEXT][HINT](URL)
:Link-Site:[TEXT][HINT](Major-ID, Minor-ID, Section-ID, Page-ID)
```

>> In second format, all elements are optional except TEXT and HINT (in that case, it'll point to home page), but when elements are present they should be in specified sequence separated with commas

> For example:
> 
>> #Para: Click :Link-URL:\[here\]\[here\](https://ubrant.com) for learning amazing things
> 
> will be displayed as
> 
>> Click [here](https://ubrant.com) for learning amazing things

Links can be placed anywhere inside text elements, as only TEXT will be placed alongside other text in regular flow of document content.





---





## Code

"**#Code: language**" at beginning of any line will denote starting a code-block. Whereby, all subsequent lines will be considered as the part of same code-block.

> For example:
> 
>> #Code:
>> 
>> int a = 5;
>> 
>> int b = 6;
>> 
>> int sum = a + b;
> 
> will be displayed as
> 

```
int a = 5;
int b = 6;
int sum = a + b;
```

>> **Note:** Following part of code tag line will define the coding language, so it can be skipped => start code-block from next line

"**#Console:**" at beginning of any line will denote starting console output. Whereby, all subsequent lines will be considered as the part of same output.

>> **Note:** Initial and ending blank lines will be trimmed and wont produce any output

> For example:
> 
>> #Console:
>> 
>> C:\>dir
> 
> will be displayed as

```
C:\>dir
```





---





## Questions

Testing of user's knowledge can be done by requiring to answer questions at any time. For this purpose, following format is supported **inside a Page**:

```
@Question
    #Difficulty: Difficulty Level
    #Text: Question Text
    #OptA: Option "A" Text
    #OptB: Option "B" Text
    #OptC: Option "C" Text (Optional)
    #OptD: Option "D" Text (Optional)
    #OptE: Option "E" Text (Optional)
    #OptF: Option "F" Text (Optional)
    #OptG: Option "G" Text (Optional)
    #Attempts: Number of Allowed Attempts
    #Answer: Correct Option(s)
    #Explanation: Text to Describe the Correct Option(s)
```

Questions can be mixed with normal flow of document, and can be separated in different dedicated pages - thereby, will be sorted per page identifiers.

Parameters' description is as follows:

> Difficulty Level
>> ⟾ **Easy**, **Medium**, **Hard**

> Question Text
>> ⟾ Question being asked

> Option "-" Text
>> ⟾ Text to display as option, blank text will disappear option

> Number of Allowed Attempts
>> ⟾ Number (e.g., **1** if repetition is not allowed)

> Correct Option
>> ⟾ Option (e.g., **B** if Option B is correct)

> Explanation
>> ⟾ To describe about correct option

Following example defines a simple question:

```
@Question
    #Difficulty: Easy
    #Text: Did Christopher Columbus invent America?
    #OptA: True
    #OptB: False
    #Attempts: 1
    #Answer: B
    #Explanation: America was there to be discovered, not to be invented by any humanbeing
```

>> If any text or other material is present on a page before or after the question, it will be dealt with as a separate entity -- not mixed with question itself





---





## End

It's not final format, more elements will be added upon requirement.

