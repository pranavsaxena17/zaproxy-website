---
# This page was generated from the add-on.
title: Automation Framework - Environment
type: userguide
weight: 2
---

# Automation Framework - Environment

This section of the YAML configuration file defines the applications which the rest of the jobs can act on.

```
env:                                   # The environment, mandatory
  contexts :                           # List of 1 or more contexts, mandatory
    - name: context 1                  # Name to be used to refer to this context in other jobs, mandatory
      urls:                            # A mandatory list of top level urls, everything under each url will be included
      includePaths:                    # An optional list of regexes to include
      excludePaths:                    # An optional list of regexes to exclude
      authentication:                  # TBA: In time to cover all auth configs
  parameters:
    failOnError: true                  # If set exit on an error         
    failOnWarning: false               # If set exit on a warning
    progressToStdout: true             # If set will write job progress to stdout
  vars:                                # List of 1 or more custom variables to be used throughout the config file
    myVarOne: CustomConfigVarOne       # Can be used as ${myVarOne} anywhere throughout the config
    myVarTwo: ${myVarOne}.VarTwo       # Can refer other vars    
```

System environment variables can also be used in the config in the same manner as above. In case there are two variables with the same name, the value of the system variable would be preferred.
