# FlywaySbt
This version of the Flyway SBT Plugin fixes issue *can't migrate as long as there are compile errors* https://github.com/flyway/flyway/issues/979 .

    I try to flywayMigrate but there are compile errors.
    So the migrate task is never executed.
    
    The funny thing is, that i can only generate the proper code with jooq after i migrated the database.
    
    Is there a way get around the compile dependency?


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
