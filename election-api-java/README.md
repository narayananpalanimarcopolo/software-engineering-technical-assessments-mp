## Description

If you are not familiar with how elections work in the UK, please see this short BBC video https://www.youtube.com/watch?v=cRxUhGetEPQ

The results API presents a simple elections result service.

### Domain
The domain for the election represents some key concepts:
- _**constituencyId**_ a unique integer id to identify a location. E.g "Brent Central" is 90
- _**party**_ is a short 3, or 4, letter code for a party for instance LAB = Labour, CON = Conservative etc.
- _**votes**_ the number of votes gained by a party in a constituency
- _**share**_ the % share of the total votes the party received

### API
The API has 3 endpoints:
- GET `/result/{id}` to get an elections result for a given id.
- POST `/result` to add a new result
- GET `/scoreboard` to get the running totals. This is unimplemented.


## Prerequisites
- Java 11

### Please ensure that the project builds without error within your choice of IDE. This should require no changes to the files in this repository.
### To Build
macOS / 'nix

`./gradlew build` or `./mvnw install`

Windows:

`gradlew.bat build` or `./mvnw.cmd install`

### To Run
macOS / 'nix

`./gradlew bootRun` or `./mvnw spring-boot:run`

Windows:

`gradlew.bat bootRun` or `./mvnw.cmd spring-boot:run`

### To Test
macOS / 'nix

`./gradlew test` or `./mvnw test`

Windows:

`gradlew.bat test` or `./mvnw.cmd test`

## Assessment Time: 3 Days

## Assessment Process

In the assessment process, after making changes in your github repository, we will ask you to share your working environment and talk through the following with us in a recorded video (shared via youtube link (uploaded as 'PRIVATE and reachable only via link' may be):

- Please create a github repository of your own and share your assignment as a repository, detail the code changes in readme file and share the youtube link within readme.

If you have any problems with any of the above, please get in touch via your recruitment contact.

Please feel free to send the assessment response as a link via recruitment contact
