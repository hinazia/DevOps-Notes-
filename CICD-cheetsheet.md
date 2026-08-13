### md vs yml
- md is MarkDown file meaning, go in depth explaination in detail in palin text
- yml is Yet Another Mark Up file meaning, a file written in Key value pairs. usually use for configuration

### Triggers

#### On Pull Request
```
on:
    pull_request:
        branches: [main] / trigger condition 
```

#### On Push  Request
```
on:
  push:
      branches: [main] / trigger condition 
```

#### Schedule Trigger
```
on: 
  schedule:
      - cron: '10 2 * * *'   
```

#### Manual Trigger
```
on: 
    workflow_dispatch:
        inputs:     # defines a form field GitHub shows you before running. Here, one field called environment.
            environment:
                description: "Environment to deploy to"
                required: true  # have to select the option 
                type: choice    # turns that field into a dropdown instead of free text
                options:
                    - Production
                    - Deployment
```
