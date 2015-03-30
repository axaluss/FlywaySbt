# FlywaySbt
This version of the Flyway SBT Plugin fixes issue https://github.com/flyway/flyway/issues/979 .

Also the plugin works now purely with SBT.

sources from https://github.com/flyway/flyway/tree/master/flyway-sbt 

## Usage in Project build
add this to `project/project/build.scala`:

  import sbt._
  
    object MyBuild extends Build {
    
      lazy val root = Project("root", file(".")) dependsOn(FlywaySbt)
      lazy val FlywaySbt =
           RootProject(uri("git://github.com/axaluss/FlywaySbt.git"))
    
    } 
Now you can start SBT and use all commands described in http://flywaydb.org/documentation/sbt/


## Usage
http://flywaydb.org/documentation/sbt/
