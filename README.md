# Java-Annotation-Processor-guide
This is guide for annotation processing using gradle

I spent 3 days trying to deal with it, but with this little tutorial you will made JAP in 5 minutes.

sorry for bad english :)

# So, first you should do is create gradle subproject for your project: 
  1) create project itself with `gradle init` or intellij
  2) add to your main project's `settings.gradle` file this line `include "*your subproject name, lets say:*annotation-processor"`
# Congrats, now let go to the processor itself
  1) here is so much tutorials on the web about this part, so you can read something like this https://www.baeldung.com/java-annotation-processing-builde,<br/>
  or this (Если ты русский): https://habr.com/ru/company/e-legion/blog/206208/
# Final step is very easy - you will add your annotation processor to main project.
  !!! instead of `annotation-processor` you should use your subproject name !!! <br/>
  
  kotlin (or java + kotlin) -> {<br/>
    add this plugin to your plugins: `id "org.jetbrains.kotlin.kapt" version "1.7.21"`<br/>
    add this to your dependencies:<br/>
    `kapt project('annotation-processor')`<br/>
    `compileOnly project('annotation-processor')`<br/>
  }<br/>
  java -> {<br/>
    add this to your dependencies:<br/>
    `annotationProcessor project('annotation-processor')`<br/>
    `compileOnly project('annotation-processor')`<br/>
  }<br/>
