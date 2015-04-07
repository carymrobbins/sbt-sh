sbt-sh
======

Using the sbt-sh plugin you can invoke shell commands:

	> sh git status
	# On branch master
	nothing to commit (working directory clean)
	> 

Happiness and productivity ensues without the hassle of exiting sbt or opening multiple terminals.  


Installing
----------

Right now you must build from source.  After cloning, you can run -

    sbt publishLocal

Now you can enable this plugin globally by adding the following to *~/.sbt/0.13/plugins/build.sbt* -

    addSbtPlugin("org.sbtsh" % "xsbt-sh" % "0.1-SNAPSHOT")

Usage
-----

The sbt-sh plugin introduces a *sh* command to sbt, this will execute the rest of the line as a shell command:

	> sh ls
	build.sbt
	LICENSE
	project
	sbt
	sbt-launch-0.10.0.jar
	src
	target
	>

	> sh ls -l
	total 940
	-rw-r--r-- 1 swells developers     66 Jun  9 15:08 build.sbt
	-rw-r--r-- 1 swells developers   1394 Jun  9 15:08 LICENSE
	drwxr-xr-x 4 swells developers   4096 Jun  9 15:23 project
	-rwxr-xr-x 1 swells developers     69 Jun  9 15:08 sbt
	-rw-r--r-- 1 swells developers 935142 Jun  9 15:08 sbt-launch-0.10.0.jar
	drwxr-xr-x 3 swells developers   4096 Jun  9 15:08 src
	drwxr-xr-x 3 swells developers   4096 Jun  9 15:23 target
	>

	> sh cat build.sbt
	sbtPlugin := true
	
	name := "xsbt-sh"
	
	organization := "org.sbtsh"
	> 
