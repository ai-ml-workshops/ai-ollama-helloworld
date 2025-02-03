### This is a basic example of a barebone chatbot app built using Java, with the following tools:

- Spring AI
- Spring Boot (not using autoconfigure)
- Ollama (running LLM locally)
- JDK 23 
> *Note* If you are using an earlier version of JDK, for example, 21, you may run into runtime problems possibly caused by incompatibilities among the Spring libraries and JDK.
>> In such case, first please update the version of Java in the pom.xml:
>> - \<java.version\>21\</java.version\>
>> 
>> Then, lower the version of your Spring web starter version to a version such as:
>> + \<artifactId\>spring-boot-starter-web\</artifactId\>
>>    + \<version>3.2.12\</version>
>

****
### To build it:

- `mvn clean install`

### To run it:

- `mvn spring-boot:run`


### To use the chatbot:

1. Make sure that your **SPRING_AI_OPENAI_API_KEY** is set in .src//main/resources/application.properties

2. Make sure that you have Ollama up and running the LLM that you've selected to use.  The default LLM that we are using for this exercise is **gemma2**. Please be sure to also download the LLM beforehand.  For more information on how to install and work with Ollama, please see its [README](https://github.com/ollama/ollama/blob/main/README.md)

_Note: Since the LLM is run locally, there will not be any charges but the OPENAI_API_KEY is still required_

Now that you've got all the ducks in a row, you are ready to try this chatbot:
>`curl --get --data-urlencode 'messsage=Tell me a joke' localhost:8008/ai/ollama/chat`

##### Note: You can also use the HTTP client, like so:
> http://localhost:8080/ai/ollama/chat?message='tell%20me%20a%20joke'

---> Try asking different questions and be entertained :)