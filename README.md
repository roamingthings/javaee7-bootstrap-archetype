# JavaEE 7 with Twitter Bootstrap maven archetype

This projects builds a maven archetype to generate a JavaEE 7 project using [Twitter Bootstrap](http://getbootstrap.com) to render JSF pages.

The generated project comes with the sources of Twitter Bootstrap, a configuration class for JAX-RS endpoints and some
 basic jsf pages for error handling and startup.

Twitter Bootstrap Version: 3.3.6

## What's inside

The generated project will contain the following configured components:

* Page template using bootstrap at `/src/main/webapp/contracts/default/template/page.xhtml`
* Sample pages (configured in `web.xml`)
    * `/index.xhtml` - Configured as welcome page
    * `/404.xhtml` - Configured as 404 page
    * `/500.xhtml` - Configured as 500 page
    * `/expired.xhtml` - Configured for expired views
* JAX-RS configuration (default path `/api`)

## Usage

To setup a new project execute the following maven

```bash
mvn archetype:generate -Dfilter=de.roamingthings:javaee7-bootstrap-archetype
```

The following variables are available during the generation process:

 * `contextRoot` - The context root of the generated artifact when deployed in JBoss WildFly
 * `developerName` - Name of the developer used in various locations
 * `developerEmail` - Email address of the developer used in various locations

 The package name will be used as a base package for the generated JAX-RS configuration class.

### Configuring the JSF project stage

The `pom.xml` file generated for the project contains two profiles that can be used to build the resulting project in
the _development_ or _production_ state. This can be done by calling `mvn -Pproduction [target]` or
`mvn -Pdevelopment [target]`.

The `web.xml` deployment descriptor will be filtered and copied during the build process and can be found in
`/src/main/filtered-webapp/WEB-INF`.
