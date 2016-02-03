*NOTE*: This project is mostly superseded by [script-oak](https://github.com/mduerig/script-oak)

This is the [Ammonite-REPL](https://lihaoyi.github.io/Ammonite/) with
[Jackrabbit Oak](http://jackrabbit.apache.org/oak/) dependencies embedded in
a single executable jar.

Building the shell with  [Maven](http://maven.apache.org/):

    mvn clean install

Starting the shell

    java -jar oak-shell-*.jar

opens an interactive Scala shell with all Oak dependencies already there. To
create a new repository and open a session try this:

     val jcr = new org.apache.jackrabbit.oak.jcr.Jcr
     val repo = jcr.createRepository
     val creds = new javax.jcr.SimpleCredentials("admin", "admin".toCharArray)
     val session = repo.login(creds)
     val root = session.getRootNode
     root.addNode("foo")
     ....

