## ![NekoShlink Logo](images/nekoshlink.png) Welcome to NekoShlink

NekoShlink is a URL Shortener - it belongs to the same category as [Bitly](https://bitly.com/)
and [TinyURL](https://tinyurl.com), but unlike them, it is completely open source and free.

It offers the following features, aside from the obvious ability to make long complex URLs shorter :smirk:

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

### The Beginnings

NekoShlink was inspired by [Shlink](https://shlink.io). Shlink is a URL Shortener written in PHP. I was using it for my 
own short URLs, the ones I create and hand out for my training events, but over time I realized I wanted more out of 
the software - there were features other shorteners had that were not going to be implemented in Shlink, so... I decided
to rewrite it myself using Spring Boot.

I also noticed that there was no open-source URL Shortener product targeting any of the JVM languages, which meant my 
rewrite could also help feel a gap.

### Pluralsight Course

In June 2021 I was given the opportunity to write another course for Pluralsight (my fourth one) and the topic was 
_Securing REST Services Using Spring Security 5_ - it seemed almost like fate, as I had just completed the core development
on NekoShlink, and I was about to embark on the task of securing the product using Spring Security.

Therefore, NekoShlink is the main subject of a Pluralsight course, too!

### NekoShlink High-level Architecture

The main code base of NekoShlink is made up of three Spring Boot Gradle projects

- The `shlink-core` library project
- The `shlink-cli` console-based project
- The `shlink-rest` web-based project

This main code base offers a fully functional, albeit unsecured product. Full authentication and authorization support,
with various options, is provided by a separate project

- The `shlink-security` library project
- The optional `shlink-oauth-server` web-based project provides an OAuth2 auth server based on the Spring Security 
Auth Server code base

Finally, another project contains miscellaneous utility classes that are more general and do not apply specifically to
NekoShlink

- The `nekosoft-utils` library project
