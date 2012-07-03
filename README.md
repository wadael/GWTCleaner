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


Tested with Eclipse 3.7 win32

Thanks mudelta for the patch on the manifest, that removed a few install steps 

Jerome Baton
@wadael

