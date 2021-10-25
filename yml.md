---

title: YAML Errors and How to Avoid Them
layout: col-sidebar
permalink: /www-staff/yml/

---


The OWASP Foundation website has a large number of pages that use YML (pronounced YAMEL, like camel). YML is a simple, human-readable text format for presenting data. The YML specification is outside the scope of this document but you can read more about it [here.](https://yaml.org/spec/)

While YML is simple and easy to read, it also requires specific formatting which can cause consternation if not careful. In order to help understand the common issues experienced with YML and how to fix them, here are the top causes of YML errors in our files:

### Improper indentation
As mentioned, YML is very unforgiving if the specification is not followed and nowhere is this more evident than with indentation. Here are a number of examples of common indentation errors:
Improper indentation of top-level items
Top level items are the items to the far left of the YML file. The very first item always begins with a -.  For instance, consider the following:
```
- Title: This is my title
  Name: This is my name
  Description: This is my description
```

 	In this example, the top level items are Title, Name, and Description. These three are 
considered one ‘data item’. If we add another top level data item it would look like:
```
- Title: This is my title
  Name: This is my name
  Description: This is my description
- Title: This is my second item title
  Name: This is my second item name
  Description: This is my second item description
```

  	What frequently happens is that these top-level items are off by one or more spaces, 
either to the left or to the right. This will cause an error when the site builds. For 
instance, in the following example the Name is indented one space too many:
```
- Title: This is my title
   Name: This is my name
  Description: This is my description
```

Something worth noting here is that, if your text spans more than one line, it must also be indented from the name of the data item, though the amount of this indentation is much more forgiving and can vary. In the following example, the data item named ‘Description’ has multiple lines and these lines are indented beyond Description’s level:
```
- Title: This is my title
  Name: This is my name
  Description: This is my very long description that goes beyond a single line and 
    so should really be treated somewhat differently. In fact, it is better, for 
    lengthy lines to use the >- method which will be discussed later.
```

Improper indentation of secondary, tertiary, etc level items:
This is very similar to the above for top-level items. Secondary level items, or sub-items, 
are started with a - character similar to top-level items. Note the following example 
where we start a sub-item called Items:
```
- Title: This is my title
  Name: This is my name
  Description: This is my description
  Items:
  - ItemName: My Item Name
    ItemDescription: My Item Description
    Image: My Item Image
  - ItemName: My Item Two Name
    ItemDescription: My Item Two Description
    Image: My Item Two Image
```

	These sub-items must follow similar rules as the top-level items in that they must begin 
on the same indentation level with each other, like above. The following misalignment of 
items will produce an error:
```
- Title: This is my title
  Name: This is my name
  Description: This is my description
    Items:
      - ItemName: My Item Name
        ItemDescription: My Item Description
        Image: My Item Image
      - ItemName: My Item Two Name
        ItemDescription: My Item Two Description which is very long and also will produce an error 
        because it doesn’t line up under ItemDescription.
    Image: My Item Two Image
```

There are several errors in the above example. The first is the ItemDescription for Item two doesn’t align with the ItemName. Likewise, the Image in item two does not align with ItemName. Finally, there is an error in the ItemDescription because the second line does not indent beyond ItemDescription. Correcting the above example produces:
```
- Title: This is my title
  Name: This is my name
  Description: This is my description
  Items:
    - ItemName: My Item Name
      ItemDescription: My Item Description
      Image: My Item Image
    - ItemName: My Item Two Name
      ItemDescription: My Item Two Description which is very long and also will 
		     produce an error because it doesn’t line up under ItemDescription.
      Image: My Item Two Image
```

### Non-paired double quotation marks
Non-paired double quotation marks can also cause build errors. It is important to discuss why we would use quotation marks at all in our YML files; mainly this occurs if 1.) the text contains quotation marks anyway or 2.) there are special characters within the text that YML uses as keywords that must be inside quotation marks (except when using >-, but we will get to that later). The most notorious of these key characters is the colon. The following would be an error:
```
- Title: This is my title with: a colon
  Name: This is my name
  Description: This is my description
```

So, how do we get around that? One way is to encapsulate the text after Title in quotation marks, like so:
```
- Title: “This is my title with: a colon”
  Name: This is my name
  Description: This is my description
```

However, this produces the possibility that we forget to match our quotation marks. The following is such an example and will produce an error:
```
- Title: “This is my title with: a colon
  Name: This is my name
  Description: This is my description
```

Beginning a data item with “ requires a matching, ending “. However, we can get around the use of quotation marks completely by using >-, as in the following example:
```
- Title: >-
    This is my title with: a colon
  Name: This is my name
  Description: This is my description
```

But, of course, that looks ridiculous because the title is so short. Using >- is best used with long text as in the following:
```
- Title: “This is my title with: a colon”
  Name: This is my name
  Description: >-
           This is my very long description that goes beyond a single line and 
           so should really be treated somewhat differently. In fact, it is better, for 
           lengthy lines to use the >- method which will be discussed later.
```

So, use quotation marks when the text is short and contains special characters like above. Otherwise, use >-

### Double quotation marks inside double quotation marks
Quotation marks within quotation marks usually happens when the line contains a special character like : AND contains a quoted bit of text like in the following example, which will produce an error:
```
- Title: “This is my title: a “talk” about life.”
  Name: This is my name
  Description: >-
    This is my very long description that goes beyond a single line and 
    so should really be treated somewhat differently. In fact, it is better, for 
    lengthy lines to use the >- method which was discussed previously.
```

Here, the Title data item contains a bit of text with a : and also quotation marks around “talk”. The best way to handle this error is to remove the inner double quotation marks and use single quotation marks instead:
```
- Title: “This is my title: a ‘talk’ about life.”
  Name: This is my name
  Description: >-
    This is “my very long” description: it goes beyond a single line and 
    so should really be treated somewhat differently. In fact, it is better, for 
    lengthy lines to use the >- method which was discussed previously.
```

Note that, in the above example, there are double quotation marks AND a : in the Description. This is okay because Description is using the >- method as recommend for long text.

### Using reserved characters like : in non-quoted lines
As mentioned previously, using special characters like : requires the use of quotation marks around the text. However, because it is discussed thoroughly, above, we will not go into details here.

### Using editor-specific double quotation marks characters for ONE of the characters instead of keyboard double quotation marks
This one is perhaps the most difficult to find and also the most uncommon. There are popular document editing applications that, due to font or other issues, use two separate characters for begin quote and end quote. This causes an error in YML. Note the following:
```
Title: "Hello, World”
  Name: This is my name
  Description: >-
    This is “my very long” description: it goes beyond a single line and 
    so should really be treated somewhat differently. In fact, it is better, for 
    lengthy lines to use the >- method which was discussed previously.
```

The begin quote and end quote around Hello, World are different style quotation marks (this is really difficult to tell). You can fix this error by re-typing the quotation marks once you copy-paste from an external editor. Like so:
```
- Title: “Hello, World”
  Name: This is my name
  Description: >-
    This is “my very long” description: it goes beyond a single line and 
    so should really be treated somewhat differently. In fact, it is better, for 
    lengthy lines to use the >- method which was discussed previously.
```

So, essentially, if all else fails, re-type begin and end quotation marks.

### Made it this far!? Congratulations! You are on your way to editing YML like a pro.
