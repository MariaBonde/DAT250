### Report on expass 7
Getting rabbitMQ to work on my mac was really a challenge. I get a classdefnofounderror no matter what I do. I have both 
loaded the slf4j and amqp-client as dependencies in pom.xml, I have added the downloaded jars into my library, and I
have added them to the classpath on my machine. I still get the same exact error.
Writing everything with their absolute path worked for the first compiling command: 
``` javac -cp /Users/mariabonde/.m2/repository/com/rabbitmq/amqp-client/5.7.1/amqp-client-5.7.1.jar src/main/java/Send.java src/main/java/Recv.java```

When I run the next command
```java -cp .:amqp-client-5.7.1.jar:slf4j-api-1.7.26.jar:slf4j-simple-1.7.26.jar src/main/java/Recv.java```

I get errors on all the imports and all the code using the imports, as the dependencies are not found. 
When I added the three dependencies to the classpath in the project, and then replaced them with $CLASSPATH in the
command above, I got a connection refused, because I had to start the server. After finding out how to start the server, it
worked. But every time I open a new terminal window, I have to add the dependencies to the classpath again. 

The rest of the tutorial went pretty smoothly but it is tedious  to test.

My github-repository is: https://github.com/MariaBonde/rabbitMQ
