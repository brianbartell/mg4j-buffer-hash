# mg4j-buffer-hash
Minimal Perfect Hashes using Buffers rather than arrays

Contents
--------

README.txt           _ this file.
src                  _ java source files.
mg4j-buffer-hash.jar _ JAR file of compiled sources
JSAP-2.1.jar         _ JAR file for v2.1 of JSAP
mg4j-2.0.1.jar       _ JAR file for v2.0.1 of MG4J
  
Description
-----------

This package implements Minimal Perfect Hashes using Buffers rather than java arrays.
It therefore allows the data to be backed by MemCache, Random Access Files, and
data stores other than in-memory arrays.

It is an adaptation of Minimal Perfect Hashes in version 2.0.1 of
MG4J (Managing Gigabytes for Java), a free full-text search engine for
large document collections written in Java.

MG4J is free software distributed under the GNU Lesser General Public
License.


Usage
-----

  SVMTagger tagger = new SVMTagger( SVMUtil.carr( file.getCanonicalPath() ) ) ;
  tagger.execute( new Callback() {
    int i=0;
    String sentence[] = { "The", "quick", "brown", "fox", "slept", "deeply" } ;
	public Object getNextWord() { return i>=sentence.length ? null : sentence[i++] ; }
	public void wordTagged( Object appData, String word, String tag ) { System.out.println( word + "\t" + tag ) ; }
	public void sentenceUntagged( Object appData, String sentence ) { System.out.println( sentence + "\t" + "UNKNOWN" ) ;}
  } ) ;


CONTRIBUTING:
=============

The mg4j-buffer-hash library is licensed under LGPL , which means that it may be linked to and used by commercial software packages. But the license also enforces that any changes or improvements made to the library (and in this case also to the morphological data) must be redistributed under LGPL terms.

Thus, if you improve the software or data, either adding new functionalities, fixing bugs, or adding analyzers for new languages, you can not distribute them under different conditions than those stated in the license (i.e. freely and with no usage restrictions).

