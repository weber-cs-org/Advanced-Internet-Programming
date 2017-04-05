# HTML as a Semantic Language #

## HTML5 Content Organization Tags ##
HTML Documents are usually divided into sections. HTML5 introduced several logical section tags which help identify which parts of the document are unique content and which parts provide branding, navigation and other ancillary information.

`<header>`  
Describes the heading/intro content of the document. Headers are most often consistent (or at least very similar) across a site or site-section. Headers would typically include:
 * Company logo
 * Organization-wide navigation

`<footer>`  
Footers are usually site wide and contain contents such as:
Legal links (disclaimer, privacy policy, etc)
 * Contact information
 * Document modification date

While you might assume that a document only contains one header or footer, that’s not always the case. For instance you could have an organizational header followed by a unit/product header. Using Microsoft as an example, a product information page might be organized such as:
 * Main header: Microsoft logo and site-wide search
 * Second header: Internet Explorer logo and header - includes links to product versions
 * Page Content
 * Footer 1 - Support options for Internet Explorer
 * Footer 2 - Microsoft privacy policy

`<nav>`  
Navigation tags help identify sections of your page that are used for navigation. Nav tags aren’t limited to just main links. All of the following could potentially be contained in a navigation tag:
 * Main site links
 * Search
 * Sitemap or alphabetic index links
 * Contact, legal and policies

`<section>`, `<article>`, `<aside>`  
Used to subdivide content on a page. A *section* is made up of one or more *articles* (or other content). A *section* should directly correlate to an outline (if one exists) of the document.
 
An *article* is a grouping of content related to a single subject or topic. It can contain multiple paragraphs, images, lists, headings, etc.

An *aside* is used to provide tangential content. The type of content contained is determined by context. An *aside* can be used to markup “sidebar” content and for such uses should NOT be nested inside an *article*. When nested inside an *article*, an *aside* is assumed to provide tangential content directly related to the subject/topic of the *article*.

### Real World Example - A Magazine ###
 * Table of contents
 * Articles grouped by section
 * Interesting facts next to an article (asides)

## Search Engine Optimization ##
There is no substitute for good content. However good content with improper markup suffers as well.

### The Page &lt;title&gt; ###
Page titles play an enormous role in content discoverability and should ideally be unique on a site. In addition, page titles often function as a mini breadcrumb and also can contain the section and site name. In these cases, the page title should be structured from most specific to least specific so that when truncated, the title still reflects the content of the specific page:

**Wrong Example**

```HTML
<title>Computer Science - Advanced Internet Programming - HTML as a Semantic Language</title>
```

Would display in a search result as:

> *[Computer Science - Advanced Internet Programming…](#)*  
> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus sed feugiat ipsum, et euismod quam. Proin semper quam sed vulputate feugiat. Nunc sit amet ultricies ligula.

The portion of the page title related to the page content was truncated. Instead, list the most specific portion first.

**Correct Example:**

```HTML
<title>HTML as a Semantic Language - Advanced Internet Programming - Computer Science</title>
```

### Link Text ###
One of the single most abused phrases online is the words “click here.” In fact, you should almost never use these words. The target document of a hyperlink should be described by the linked text. In fact, most modern search engines return page results based partially on the words other pages used when linking to the result.

**Wrong Example:** For more information on HTML5 tags, [click here](#).  
**Correct Example:** [More information on HTML5 tags](#). 

As a programmer, you will often be given the content of a page (especially the copy text). Writers will often unknowingly replicate the bad practices they see online. You may need to work with the writer to correctly translate the text from a print (or other media) to correct web copy.

## Headings Should Be Properly Nested ##
Headings on a page describe an outline. They should produce a well-structured tree based on their code order and level. Level one headings are almost always reserved for the primary title of a page (which should replicate the first part of the title tag).

`sections` of a page will often have a heading directly nested to describe a grouping of content (such as a set of articles).

Real World Example: Wikipedia Articles

## WYSIWYG Editors and Generated Code ##
Equally loved and maligned, HTML editors provide a way for non-programmers to generate HTML content. WYSIWYG editors excel, and often produce excellent code, for article content entry - especially when not used for visual styling. They rarely produce good code when used to create the entire document.

On any major site, some type of content management system is employed to manage the site wide template code. Usually the template itself will be maintained by hand, but the content within the page is often generated by an editor. When well crafted, this setup can produce an excellent site that is easily maintained.

## Accessibility ##
WCAG 2.0 Guidelines
http://www.w3.org/TR/WCAG20/

Alt tags, tables, reading order.