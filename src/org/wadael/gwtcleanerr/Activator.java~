package org.wadael.gwtcleaner;

import java.io.File;
import java.io.FileFilter;

import org.osgi.framework.BundleActivator;
import org.osgi.framework.BundleContext;

public class Activator implements BundleActivator {
	/**
	 * All files whose names start with those strings will be erased.
	 */
	static String[] GWT_PREFIXES  = {"uiBinder_","gwt"};
	static String FOLDER_TO_CLEAN = System.getProperty("java.io.tmpdir");
	
	FileFilter toBeDeletedFiles_fileFilter = new FileFilter() {
	    public boolean accept(File file) {
	        for(String prefix : GWT_PREFIXES){
	        	if(file.getName().startsWith(prefix)) return true;
	        }
	        return false;
	    }
	};
	
	/*
	 * (non-Javadoc)
	 * @see org.osgi.framework.BundleActivator#start(org.osgi.framework.BundleContext)
	 */
	public void start(BundleContext context) throws Exception {
		cleanGWTTempFiles();
	}
	
	/*
	 * (non-Javadoc)
	 * @see org.osgi.framework.BundleActivator#stop(org.osgi.framework.BundleContext)
	 */
	public void stop(BundleContext context) throws Exception {
		cleanGWTTempFiles();
	}

	
	/**
	 * Removes all gwt files in temp folder, based on prefixes  
	 */
	public void  cleanGWTTempFiles(){
		File toBeCleaned = new File(FOLDER_TO_CLEAN);
		File[] extraFiles = toBeCleaned.listFiles(toBeDeletedFiles_fileFilter);
		int counter = 0;
		int errors  = 0;
		long sizesSum = 0;
		
		for(File erase : extraFiles){
			long size = erase.length();
			if(erase.delete()) {
				sizesSum += size ;
				counter++;
			}
			else {
				System.out.println(  "Error on " + erase.getName()  );
				errors++;
			}
		}
		System.out.println("GWTCLEANER - erased " + counter + " files (that is "+ (sizesSum /(1024*1024)) +"MB (errors: " + errors +" -- must be files in use) _ by @wadael" );
	}
	


}

