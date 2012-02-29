#What is Summer?

Summer is yet another microframework for makings simple websites using Groovy. 

Summer's goal is to provide an easy to understand, easy to use web framework on top of concepts like [KISS](http://en.wikipedia.org/wiki/KISS_principle), [YAGNI](http://en.wikipedia.org/wiki/YAGNI), [SOLID](http://en.wikipedia.org/wiki/SOLID) and built with [Agile Methodologies](http://agilemanifesto.org/) in mind.

##A little bit of context

Summer, obviously, is not an original idea. It's based on [Silex](http://silex.sensiolabs.org/) (PHP) and [Ratpack](https://github.com/bleedingwolf/Ratpack) (Groovy) which are based on [Sinatra](http://www.sinatrarb.com/) (Ruby).

Summer is also helping me learn about Java servlets, servlet containers, caching and other stuff that interests me.

##Hello World!

```groovy
Summer s = Summer.create()
s.get '/', { render views.hello }
SummerServer.factory(s).run();
```

Assuming that there is a *hello.html* template in *views* folder, this piece of code will start a Jetty server on port 8090 and will serve some content on / path.

It's that simple. Actually, there's no need for you to use the bundled View collection at all. You only need to know that the result of that closure is going to be casted to String and used as the Servlet's response content.

For more information take a look to the code starting from *SummerRunner.groovy* and contact me if you have any question.

#Templating

Summer uses [Mustache](http://mustache.github.com/) for templating.

Mustache is a cross-language interpreted templating language that supports just what you need to express websites in html **and** it implements template extension through partials.

Also, Mustaches are great!

##Why not Groovy's SimpleTemplate

Because, it has too many features and it doesn't have inheritance/extension mechanisms (as far as I'm aware of, please, correct me if I'm wrong). 

#Current status of Summer

Current version is a much-glorified spike that meets the minimum  features that I wanted Summer to include: It comes with an embedded server and it has an external file, text based, interpreted templating engine.

Its architecture makes it possible to evolve towards something that you could easily import into any project and just use it as any other dependancy. Remember that your projects should speak about them, not about the framework they use.

##Next steps

As a spike, it's going to die. Soon.

A TDDed version of Summer will replace it soon enough, providing a better documentation and coverage for future modifications.

##Missing features a.k.a. "To Do list"

Without any particular order:

 - TDDed rewrite of Summer
 - User Servlet 3.0 specification
 - Serve static content, probably like Ratpack does
 - Response caching
 - Mustache partials support
 - Simple database configuration layer using Groovy's SQL API
 - Integration with [Groomple](http://github.com/ggalmazor/Groomple) (dependancy/service container). Summer should extend Groomple and somehow this should help to build ActionContexts.
 - Replace Jetty with Winstone servlet container
 - Do some performance tests and publish the results
 - Prepare an extension API based on Groomple, like Silex does on Pimple
 - Check/Fix build definition to get a Summer.jar that you could use on other projects
 - Check/Fix Gradle's *application plugin* to actually launch Summer server
 - Prepare an example for 10.
 - Code some helpers for url generation inside templates
 - Enable PMD/Checkstyle plugins
 - Use some Continuous Integration

If there is anything that you'd want see in that list, please let me know. Also, I'll be happy to hear your thoughts on Summer anytime. Just send me an email :)