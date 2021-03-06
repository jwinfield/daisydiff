> This is a fork of Nuxeo's Mavenized version of Daisy Diff 1.2 based on the 
> official Daisy diff 1.2 release http://daisydiff.googlecode.com/svn/tags/v1.2/
> Using the work started by Nuxeo, I'm hoping that this could be the next
> home for where work on future versions can continue on this project.
> Original Daisy Diff 1.2 README content below.

# Daisy Diff 1.2

This is Daisy Diff, the open source HTML diffing library!
Website - http://code.google.com/p/daisydiff/

## Stand-alone

### Java

```
java -jar daisydiff.jar [oldHTML] [newHTML] [optional arguments]
```

#### Optional Arguments:
```
--file=[filename] - Write output to the specified file.
--type=[html/tag] - Use the html (default) diff algorithm or the tag diff.
--css=[cssfile1;cssfile2;cssfile3] - Add external CSS files.
--output=[html/xml] - Write html (default) or xml output.
--q  - Generate less console output.
```

##### Example:
```
java -jar daisydiff.jar http://web.archive.org/web/20070107145418/http://news.bbc.co.uk/ http://web.archive.org/web/20070107182640/http://news.bbc.co.uk/ --css=http://web.archive.org/web/20070107145418/http://news.bbc.co.uk/nol/shared/css/news_r5.css

java -jar daisydiff.jar http://cocoondev.org/wiki/291-cd/version/15/part/SimpleDocumentContent/data http://cocoondev.org/wiki/291-cd/version/17/part/SimpleDocumentContent/data --css=http://cocoondev.org/resources/skins/daisysite/css/daisy.css --output=xml --file=daisysite.htm
```

#### Requirements:
Java 1.5 or 6

## Embedded

### Java:
```
org.outerj.daisy.diff.DaisyDiff{

/**
 * Diffs two html files, outputting the result to the specified consumer.
 */
public static void diffHTML(InputSource oldSource, InputSource newSource, ContentHandler consumer, String prefix, Locale locale) throws SAXException, IOException;

/**
 * Diffs two html files word for word as source, outputting the result to
 * the specified consumer.
 */            
public static void diffTag(String oldText, String newText, ContentHandler consumer) throws Exception;

}
```

#### Requirements:
Java 1.5 or 6
To run Daisy Diff embedded in your application, you don't need the entire Jar file. A much smaller Jar file without Xerces and NekoHtml will suffice.

## PHP

The DaisyDiff algorithm has been integrated in MediaWiki. The version with DaisyDiff support isn't released yet.
More info on: http://www.mediawiki.org/wiki/Visual_Diff

The PHP code is released under the GPLv2. It can also be used as an embedded HTML differ in a PHP application.

## Acknowledgements

- Guy Van den Broeck <guy@guyvdb.eu>
- Daniel Dickison
- http://www.nuxeo.com
