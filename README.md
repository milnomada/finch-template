# Finch HTTP Service Template

This is a template for a simple, stateless HTTP API built on top of [Finch](https://github.com/finagle/finch). It
aims to provide a simple, consistent, beginner- to intermediate-level stack, aimed at getting a small HTTP-based
service up & running quickly with some things we care about in a production system.

It aims to provide:

* A HTTP stack, using [Finch](https://github.com/finagle/finch);
* Authentication support using [Hawk](https://github.com/hueniverse/hawk), a HMAC-style protocol;
* JSON encoding & decoding, using [Circe](https://github.com/travisbrown/circe);
* Clients for talking to downstream services;
* Centralised logging using syslog;
* Monitoring & [metrics](https://twitter.github.io/finagle/guide/Metrics.html) support using ...;
* Consistent error handling;
* Tracing with [Zipkin](https://github.com/openzipkin/zipkin);
* Testing using [specs2](https://etorreborre.github.io/specs2/) & [ScalaCheck](https://www.scalacheck.org);
* Packaging using [SBT Native Packager](https://github.com/sbt/sbt-native-packager).

# Further Reading

Here's some further reading on how this hangs together, and how to do more/extend.

* [Finch best practices](https://github.com/finagle/finch/blob/master/docs/best-practices.md)
* [Finagle 101](http://vkostyukov.net/posts/finagle-101/)
* [Finch 101](http://vkostyukov.ru/slides/finch-101/)
* [Getting started with Finagle](http://andrew-jones.com/blog/getting-started-with-finagle/)
* [An introduction to Finagle](http://twitter.github.io/scala_school/finagle.html)

# TODO

* Authentication
  * Server-Authorization header on responses.
* Metrics - http://rodrigolazoti.com.br/2015/01/08/send-finagle-stats-to-codahale-metrics-library
* Client calls to Google search
* Syslog logging
* Zipkin

# Customising

1. Take a clone.

1. TODO

# API

There is simple [API documentation](API.md).

# Setup

## Development Setup

1. Install [Java 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) from Oracle.
   You will need a JDK (not a JRE), as of the time of writing this is "Java SE Development Kit 8u92". There is also
   [documentation](http://www.oracle.com/technetwork/java/javase/documentation/jdk8-doc-downloads-2133158.html)
   available (handy for linking into your IDE).

1. Run [sbt](http://www.scala-sbt.org/release/docs/Getting-Started/Setup.html)::

    ```
    $ ./sbt
    > update
    ```

    Note. You could also `brew install sbt` if you'd prefer a system version.

## Deployment Setup

TODO

# Running

To run using sbt:

```
$ ./sbt run
```

You can also use [Revolver](https://github.com/spray/sbt-revolver) for restarts when code changes:

```
$ ./sbt ~re-start
```

# Testing

```
$ ./sbt test
```

This will start the `sbt` REPL, from where you can issue [commands](http://www.scala-sbt.org/0.13/docs/Running.html#Common+commands).

* `test` - Runs all tests, use this to check your exercises;
* `test-only workshop.exercises.scalatest.Exercise01` - Runs a single test;
* `test-only workshop.exercises.*` - Runs all tests in the `workshop.exercises` package;
* `test:compile` - Compiles your test code.

Appending a `~` to the start of any command will run it continuously; for example to run tests continuously:

```
> ~test
```

# Deployment

```
$ sbt stage
```

TODO

# Uninstall

You can uninstall everything you installed for this project by:

```
$ rm -rf ~/.sbt
$ rm -rf ~/.ivy2
```

Then, if you want, you can uninstall Java by following the instructions here: https://docs.oracle.com/javase/8/docs/technotes/guides/install/mac_jdk.html#A1096903