# Enriching Markup with Microdata and RDFa Lite #
HTML5 tags, when properly used, can add many hints as to the type of content. But HTML markup on it’s own is not enough to provide the modern search engine with information which can be reliable parsed. Snippets of page content are often shown in a search results and as search engines have evolved, these snippets have gotten more and more complex. Common examples:
 * A recipe result includes photo, description and ratings
 * A product page shows the number of user reviews
 * Smart breadcrumbs

The need for a standardized way to display structured data has long been evident, but there have been many competing ways to accomplish this.

## Microformats ##
Reusing existing HTML attributes and tags to convey semantic meaning is known as microformats. Since microformats only use existing attributes and tags, the only thing left to learn was the vocabulary or schema. Microformats were one of the first widely recognized ways to add semantic meaning to a page without altering the user display.

Microformats have traditionally suffered from several major problems:

 1. **Lack of namespaces**  
Contacts are identified with the class name “vcard”. But what if that class name was already in use on your site?
 2. **Misuse of attributes**  
Microdata often used the “rel” and “title” attributes of elements (among others) to convey semantic meaning. For instance it was recommended to use the <abbr> element for times and set the “title” attribute to the correctly formatted time for a vcard. But the title attribute is meant to be a hint or clarification of the tag (it shows on mouseover) and the vcard formatted time is more cryptic instead of less.
 3. **Small Number of Recognized Formats**  
Despite the wide adoption rate, the number of recognized formats was relatively low. In fact main usage of the format is limited to contacts (hcard) and events (hcalendar).

In addition, for a number of years the format lay dormant.

[Example microformat](http://microformats.org/wiki/hcard#Live_example)

## RDFa ##
An XML based solution, RDFa predates microformats. However it has not been widely adopted primarily due to the overly verbose and rigorous requirements. While it was favored heavily by standard authors, it has been difficult for web authors to use.

## Microdata ##
With the complaints of authors as a foundation, search engines brought concerns to the RDFa specification authors. However, calls for change went unheeded. So Google, Microsoft and Yahoo! jointly created both an easy-to-use format that worked well with HTML5 and a comprehensive vocabulary of markup. This venture was announced and is hosted at http://schema.org/. Microdata made it almost as easy to add semantic information to documents as microformats with none of the drawbacks.

[Microdata example](http://schema.org/docs/gs.html#microdata_how)

## RDFa Lite ##
The RDFa authors didn’t fully anticipate what rejection of their standard by major search engines would mean. When Schema.org was launched, the RDFa committee quickly began work on an easier to use version of RDFa known as RDFa Lite. This new version had almost a 1 to 1 mapping to the microdata properties.

The big bonus is that RDFa Lite can be used with the same vocabulary from Schema.org.

[RDFa Lite example](http://www.w3.org/TR/rdfa-lite/)

## Facebook - The Odd Man Out ##
Facebook relies heavily on their Open Graph meta tags. Of all of the strategies listed, this is the least extensible. However you can’t ignore such a behemoth. Careful crafting can leverage the same meta tags to convey both Facebook Open Graph and Microdata syntax.

```HTML
<meta name="description" itemprop="description" content="Short page description" />
<meta name="og:image" itemprop="image logo" content="http://mysite.com/images/logo.png"/>
```

## JSON-LD ##
The newest kid on the block, JSON-LD (the LD stands for Linked Data) was announced by Google for providing semantic information to Gmail. It is unclear if it has a future beyond HTML emails.

## Implementation Notes ##
Avoid duplicating information. You should always markup content that already exists on the page first. 
If you need semantic data that isn’t for display or use on the page, use a meta tag.

## Development Tools ##
 * [Google Rich Snippets Tool](http://www.google.com/webmasters/tools/richsnippets)
 * [Facebook Link Debugger](https://developers.facebook.com/tools/debug/)
 * Test with Google+ and Facebook

## Miscellaneous Notes ##
 * A unique item should only occur once on a page. In your homework assignment, there should only be one company, business or place. The itemscope or typeof attributes can go on the html tag to encompass the whole page.
 * Pages which aggregate multiple content sources onto a single page are not good candidates for this type of markup. It’s best to markup the original source of the content.
