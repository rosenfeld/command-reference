# Maven artifact for Groovy projects

For creating a Maven artifcact in non-interactive mode (parameter -B: batch mode)
which accepts both Java and Groovy sources and tests, launch this command:

    mvn archetype:generate -DarchetypeGroupId=org.codehaus.groovy.maven.archetypes -DarchetypeArtifactId=gmaven-archetype-basic -DarchetypeVersion=1.3 -DgroupId=com.yourdomain -DartifactId=your-artifact-name -Dversion=1.0-SNAPSHOT -Dname="Your Project Name" -B
