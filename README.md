# Spring Boot example app for Spring Boot and Angular2 Tutorial
 
[![Build Status](https://travis-ci.org/springboot-angular2-tutorial/boot-app.svg?branch=master)](https://travis-ci.org/springboot-angular2-tutorial/boot-app)
[![Coverage Status](https://coveralls.io/repos/github/springboot-angular2-tutorial/boot-app/badge.svg?branch=master)](https://coveralls.io/github/springboot-angular2-tutorial/boot-app?branch=master)

This repository is an example application for Spring Boot and Angular2 tutorial.

[Demo](https://micropost.hana053.com/)

* JWT
* [Querydsl](http://www.querydsl.com/)
* [Spock](http://spockframework.org/)

## Getting Started

Run Spring Boot.

```
mvn spring-boot:run
```

Serve frontend app.

```
git clone https://github.com/springboot-angular2-tutorial/angular2-app.git
# Follow the README
```

Testing.

```
mvn test
```

API documentation.

```
mvn spring-boot:run
open http://localhost:8080/swagger-ui.html
```

## Frequently asked questions

* Build becomes an error on IDE with error message "QUser, QRelationship and etc can't be found".
  * Before you open this project from your IDE, you need to build project once with mvn command. Or else, generated source by annotation processor won't be recognized correctly.
```
# It will generate target directory
mvn clean package -DskipTests=true -Dmaven.javadoc.skip=true
# After that, open this project from Intellij IDEA or Eclipse.
```

## Docker Support

Dev

```bash
mvn clean package -DskipTests=true -Dmaven.javadoc.skip=true
docker build -t IMAGE .
docker run -p 8080:8080 IMAGE
```

Prod

```bash
mvn clean package -DskipTests=true -Dmaven.javadoc.skip=true
docker build --build-arg JASYPT_ENCRYPTOR_PASSWORD=secret -t IMAGE .
docker run -p 8080:8080 \
  -e "SPRING_PROFILES_ACTIVE=prod" \
  -e "MYSQL_ENDPOINT=dbhost:3306" \
  -e "NEW_RELIC_LICENSE_KEY=newrelic licence key" \
  IMAGE
```

## Tutorial

Under construction...

## Related Projects

* [Angular2 app](https://github.com/springboot-angular2-tutorial/angular2-app)
* [Android app](https://github.com/springboot-angular2-tutorial/android-app)
* [Infrastructure by Terraform](https://github.com/springboot-angular2-tutorial/micropost-formation)
* [Lambda functions by Serverless](https://github.com/springboot-angular2-tutorial/micropost-functions)

## Credits

* [Rails tutorial](https://github.com/railstutorial/sample_app_rails_4)

## License

[MIT](/LICENSE)
