## ![NekoShlink Logo](images/nekoshlink.png) Welcome to NekoShlink

NekoShlink is a URL Shortener - it belongs to the same category as [Bitly](https://bitly.com/)
and [TinyURL](https://tinyurl.com), but unlike them, it is completely open source and free.

It offers the following features, aside from the obvious ability to make long complex URLs shorter 😏

- A Core API with CLI and REST front-ends
- Full access control of who can do what on your instance
- Several authentication methods supported
- Auto-generated and custom slugs
- Password protection of link expansion
- Support for multiple domains in the same instance
- Tagging for easier classification and searching
- Email tracking with 1px transparent image
- QR Code generation
- Visit stats

You have full access to the source code from [NekoShlink's Github repositories](https://github.com/nekoshlink) and you're
encouraged to fork and contribute!

### Getting Started

Follow [this link](get-started.md) if you want to get up and running as quickly as possible.

If you have time to spare, read on for some background info on this project...

### The Beginnings

NekoShlink was inspired by [Shlink](https://shlink.io). Shlink is a URL Shortener written in PHP. I was using it for my
own short URLs, the ones I create and hand out for my training events, but over time I realised I wanted more out of
the software - there were features other shorteners had that were not going to be implemented in Shlink, so... I decided
to rewrite it myself using Spring Boot.

I also noticed that there was no open-source URL Shortener product targeting any of the JVM languages, which meant my
rewrite could also help feel a gap. I chose Kotlin because it works well with Spring Boot, it is less verbose than Java
and as close as Scala (probably my favourite language) as is possible to get while comfortably writing Spring Boot code.

### PluralSight Course

In June 2022 I was given the opportunity to write another course for Pluralsight (my fourth one) and the topic was
[_Securing REST Services Using Spring Security 5_](https://app.pluralsight.com/library/courses/spring-security-5-securing-rest-services) - it
seemed almost like fate, as I had just completed the core development on NekoShlink, and I was about to embark on
the task of securing the product using Spring Security.

Therefore, NekoShlink is the main subject of a Pluralsight course, too!

### NekoShlink High-level Architecture

The main code base of NekoShlink is made up of three Spring Boot Gradle projects

- The `shlink-core` library project
- The `shlink-cli` console-based application project
- The `shlink-rest` web-based application project

This main code base offers a fully functional, albeit unsecured product. Full authentication and authorisation support,
with various options, is provided by separate projects

- The `shlink-security` library project
- The `shlink-userbase` library project
- The optional `shlink-oauth-server` web-based project provides an OAuth2 auth server based on the Spring Security
Auth Server code base

Finally, another project contains miscellaneous utility classes that are more general and do not apply specifically to
NekoShlink

- The `nekosoft-utils` library project
