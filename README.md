GWTCleaner
==========

Basic OSGi module to clean the files left by GWT in the temp folder. 

Will activate itself on start and stop of Eclipse.

See http://code.google.com/p/google-web-toolkit/issues/detail?id=5261

To install this :
* clone
* import in eclipse
* (optionnal) tweak the code
* do an export of the project : as a JAR
* install the plugin by dropping the JAR into $ECLIPSE_DIR/plugins
* open OSGi console (droplist in console window)
* type "ss"
* look for id of this pakage
* type "start ID"

Tested with Eclipse 3.7 linux 64

If anybody knows how to force an Activator not to be lazy an do its job, thx to tell me.


Jerome Baton
@wadael

