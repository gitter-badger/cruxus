cruxus
======

Software to help you make software!


## Configuration
Curxus can be configured by placing a ".cxconf" file in one of several directories. 

### Inherited Configuration
Below is the order in which the cruxus files inherit their configurations.
```
$CX_HOME/.cxconf
$SHARED_HOME/.cxconf                       # Inherits/Overwrites $CX_HOME/.cruxus
$USER_HOME/.cxconf                         # Inherits/Overwrites $SHARED_HOME/.cruxus
$WORKSPACE_HOME/.cxconf                    # Inherits/Overwrites $USER_HOME/.cruxus
```

### Example Configuration Values
Configuration is in Yaml format.
```
    project_id:"my_project",
    build.compiler:"jdk1.8",
    build.engine:"maven",
    workflow_dirs: [ ],
    scm:
        url: "https|ssh|file",
        username:"foobar",
        password:"",
        provider:"git"
        
```


## Extending 
What you need to implement
+ \<module-name\>
|
+--- \<module-name\>.rb



File: \<module-name\>.rb
```ruby
module <module-name>Workflow

  class <module-name> < Thor

    def self.help_desc
      'Your description goes here'
    end

    desc 'foo', 'describes foo command'
    def foo
      ...
    end
  end
end

```