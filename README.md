# Bug in Maven Javadoc Plugin
This project demonstrates a bug in [Maven Javadoc Plugin](https://maven.apache.org/plugins/maven-javadoc-plugin/)
versions 3.1.0 through 3.3.1.  When a reactor build has multiple projects with the same groupId and artifactId, even
when different versions, the javadoc fails with `Exit code: 1 - error: module not found: com.aoindustries.example`

## Issue Reported:
We have reported this as [Issue #682](https://issues.apache.org/jira/projects/MJAVADOC/issues/MJAVADOC-682).

## To Reproduce:
1. Clone this project: `git clone https://github.com/aoindustries/maven-javadoc-plugin-failing-multiple-projects-same-name.git`
2. Change to project directory: `cd maven-javadoc-plugin-failing-multiple-projects-same-name`
3. Perform build to see error in `jar` goal: `mvn clean verify`
4. Also fails with `javadoc` goal: `mvn clean compile javadoc:javadoc`

## Notes:
* Can build individual modules directly, such as `(cd module-1 && mvn clean verify)`
* Reverting to maven-javadoc-plugin version 3.0.1 makes it work
* Changing the groupId or artifactId in either module-1 or module-2 makes it work.
* Changing module names, package names, or class names in modules has no effect.
* We believe this to be distinct from [Issue #673](https://issues.apache.org/jira/projects/MJAVADOC/issues/MJAVADOC-673)

## Contact Us
For questions or support, please [contact us](https://aoindustries.com/contact):

Email: [support@aoindustries.com](mailto:support@aoindustries.com)  
Phone: [1-800-519-9541](tel:1-800-519-9541)  
Phone: [+1-251-607-9556](tel:+1-251-607-9556)  
Web: https://aoindustries.com/contact
