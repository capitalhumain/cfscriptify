CFScriptify
===========

Converts CFML tags to cfscript using pure Java.

Usage
-----

    ./build.sh
    ./test/test.rb
    ./run.sh my.cfm

See Appendix A for a list of supported CFML tags.

### Whitespace

Output line endings are LF, but CR and CRLF are acceptable as
input.  Output is indented with tabs, but I'd welcome a pull
request for spaces.

### Apologies for not using ant or maven

They both looked painfully complicated.  Maybe it was the XML.

Parser Generator
----------------

`build.sh` uses the included jar of [ANTLR4][7] to generate the
lexer and parser from `CFML.g4`.

Thanks
------

Thanks to the guys from [OpenBD][4] who wrote the [ANTLR3 grammer][5]
for CFML, I'll be leaning on it heavily as I write an ANTLR4 grammar.
According to SVN blame, that was `andy` and `alan` (perhaps
[Andy Wu and Alan Williamson][6]?).

References
----------

* [ANTLR 4 Runtime API][1]
* Useful examples:
    * [ANTLR 4 and AST visitors][2]
    * [ANTLR 4 tree inject/rewrite operator][3]
* [openbd.org][4]
    * [/trunk/src/com/naryx/tagfusion/cfm/parser/CFML.g][5] (ANTLR3 grammer)
* [cftag2cfscript][8] (similar project, but written in ColdFusion)

Appendix A: Supported CFML Tags
-------------------------------

### Supported (8)

cfabort
cfelse
cfelseif
cfif
cfloop
cfscript
cfset
cfsilent

### Not Supported Yet (21)

cfargument
cfbreak
cfcase
cfcatch
cfcomponent
cfcontinue
cfdefaultcase
cfdump
cffinally
cfflush
cffunction
cfinclude
cflocation
cflock
cflog
cfparam
cfrethrow
cfreturn
cfswitch
cfthrow
cftry

### No Plans to Support (118)

These tags either do not have convenient cfscript equivalents, have
complicated varients (eg. cffile), or are too rare to be worth the
trouble.  Pull requests, however, are welcome.

cfapplication
cfassociate
cfajaximport
cfajaxproxy
cfapplet
cfcache
cfcalendar
cfchart
cfchartdata
cfchartseries
cfcontent
cfcol
cfcollection
cfcookie
cfdbinfo
cfdirectory
cfdiv
cfdocument
cfdocumentitem
cfdocumentsection
cferror
cfexchangecalendar
cfexchangeconnection
cfexchangecontact
cfexchangefilter
cfexchangemail
cfexchangetask
cfexecute
cfexit
cffeed
cffile
cffileupload
cfform
cfformgroup
cfformitem
cfftp
cfgrid
cfgridcolumn
cfgridrow
cfgridupdate
cfheader
cfhtmlhead
cfhttp
cfhttpparam
cfimage
cfimap
cfimport
cfindex
cfinput
cfinsert
cfinterface
cfinvoke
cfinvokeargument
cflayout
cflayoutarea
cfldap
cflogin
cfloginuser
cflogout
cfmail
cfmailparam
cfmailpart
cfmap
cfmapitem
cfmediaplayer
cfmenu
cfmenuitem
cfmessagebox
cfNTauthenticate
cfobject
cfobjectcache
cfoutput
cfpdf
cfpdfform
cfpdfformparam
cfpdfparam
cfpdfsubform
cfpod
cfpop
cfpresentation
cfpresentationslide
cfpresenter
cfprint
cfprocessingdirective
cfprocparam
cfprocresult
cfprogressbar
cfproperty
cfquery
cfqueryparam
cfregistry
cfreport
cfreportparam
cfsavecontent
cfschedule
cfsearch
cfselect
cfsetting
cfsharepoint
cfslider
cfspreadsheet
cfsprydataset
cfstoredproc
cftable
cftextarea
cfthread
cftimer
cftooltip
cftrace
cftransaction
cftree
cftreeitem
cfupdate
cfwddx
cfwindow
cfxml
cfzip
cfzipparam


[1]: http://www.antlr.org/api/Java/index.html
[2]: http://stackoverflow.com/questions/14667781/antlr-4-and-ast-visitors
[3]: http://t7263.codeinpro.us/q/515024e9e8432c0426262341
[4]: http://openbd.org/
[5]: http://websvn.openbd.org/websvn/filedetails.php?repname=OpenBD&path=%2Ftrunk%2Fsrc%2Fcom%2Fnaryx%2Ftagfusion%2Fcfm%2Fparser%2FCFML.g
[6]: http://openbd.org/about/
[7]: http://www.antlr.org/
[8]: https://github.com/pirategaspard/cftag2cfscript
