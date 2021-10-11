# maven
1. Create a maven project using an archetype(multi module).
2. Explain different tags (plugins, dependency, parent, profile, properties, modules and project related(i.e. modelVersion, groupId, artifactId, packaging, version, description)) of POM file created using archetype.
3. Demonstrate the inheritance and aggregation of POM.
4. What is the purpose of mvn clean install and its usage in the project.


Plugins.. in maven most of work is based on tasks and goals and there
is a respective plugin for those.Plugins are central feature of maven and its core framework. Build Plugins provide strong build facilities
, other type of plugin is reporting plugin which are executed during site generation process

dependency..  A dependency is an essential functionality, library or piece of code that's essential for a different part 
of the code to work. maven provide this tag to manage all the required dependencies of your project including the 
transitive dependencies.you can define version and scope for the artifact.

parent..common dependencies, properties, variables ,constants can be defined in one place 
i.e. at a central project pom which is the parent pom for the child modules/poms ,child automatically posses/inherits
those properties and dependencies define in parent.
this is used to avoid redundancies or duplicate configurations using
inheritance between pom files.

profile...maven profiles area used to create profiles according to which
you can define and configure for certain kind of build. you provide set of 
configuration values which you going to use as often for a certain conditions 
and environment so you customize them under a profile tag.

properties..Maven properties are the placeholders for certain values, they come very handy
and provides more organised code. you can define a property for avalue and use it anywhere
in the pom using notation ${name}. there are various types of properties-
project properties, environment properties, Settings Properties, Java System Properties, custom properties.

Modelversion.. As you know pom means project object model and model veriosn tells us what version of 
the object model this POM is using. It contains and declares  which version of project descriptor the pom conforms to.
GroupId...the unique name/identifier of the organization or compant or group that created the project. 
The groupId is one of the key identifiers of a project and is typically domain name of you oraganisation distinguishing 
it from others.
artifactId..This tag is used to identify a artifact uniquely within a group,in other worrds its unique name of your project
by which the packaging happens.
packaging... it defines what type of packaging will be used for your projectjar .which type of artifact will be produced 
by your project, war ,ear, pom. default packaging value is jar.

version...it defines current version of your project or artifact thats going to be produced.
Description.. it is detailed description of your project which is used by maven to describe your project, so wherever
your project is displayed this description will be added there alonf with it by maven

mvn clean install ... clean commanf in has its own build lifecycle phase its one of first to be executed . clean command 
clears up your target folder containing your compiled files and data, and install command in maven builds up the project it
completes all previous phases of lifecycle which means it compiles both test and main files then packages them
and finally adds them to your local repository so it can be used as dependency in other projects locally
when you use mvn clean ,clean phase runs in each module before running the install phase for each module. making sure
that you're really compiling each module from scratch.


aggregation and inheritance are showed in the project itself where if you look it from parents side where its containing
child module tags making it aggregate at one place, whereas for perspective and usage from child module its inheritance of properties 
by parent.Project Aggregation is similar to Project Inheritance. But instead of specifying the parent POM from the module, it specifies the modules from the parent POM. 
By doing so, the parent project now knows its modules, and  if a Maven command is invoked against the parent project, that 
Maven command will then be executed to the parent's modules as well. and The Super POM is one example of project inheritance and you can
also make a pom parent and add child modules to it dependencies ,plugin lists,,plugin configuration, resources and 
other properties can be inherited.




