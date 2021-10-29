# Steps to use Travis CI (proyect: upc-202102-sw61-sale-system)
 1. Create new application on Heroku and connect to repo on GitHub
 2. Get the key of heroku on Profile -> Account Settings -> Api Key
 3. Create new file on the proyect (Procfile)
 web: java $JAVA_OPTS -Dserver.port=$PORT -jar target/*.war
 4. Create file (.travis.yml)
 language: java
 jdk:
 - openjdk8
 before_install:
 - chmod +x mvnw
 script: "./mvnw clean install"
 notifications:
    email: rodrigocallegaldos@gmail.com
 deploy:
    app: upc-202102-sw61-sale-system-1
    provider: heroku
    api_key: 
 5. Run the next command from IDEs Terminal
    travis encrypt <heroku_apy_key> --add deploy.api_key --pro
 6. Check if .travis.yml is complete with api_key
 7. Look your travis
 
## Some prerequisites
 - Have travis CLI installed on your pc
