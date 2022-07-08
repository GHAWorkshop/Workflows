# Example Workflows 
Workflows have to be placed in .github/workflows/


# Using Act
https://github.com/nektos/act
Rather than having to commit/push every time you want to test out the changes you are making to your .github/workflows/ files (or for any changes to embedded GitHub actions), you can use act to run the actions locally

## Requirements 
- act depends on docker to run workflows

## Basic Commands 
```
act --version
act --help 
# List all push workflows 
act -l 
# List the actions for a specific event:
act <specific_event> -l
# Run workflow 
act -W .github/workflows/<workflow_file>.yml <event> 
# passing envs
act -W .github/workflows/<workflow_file>.yml --env <key>=<value> push
act -W .github/workflows/<workflow_file>.yml --env-file <my_env-file>.env
# passing secrets
act -W .github/workflows/<workflow_file>.yml --secret <key>=<value> push
# run a specific job
act -j <job_name>
```

## Limitations 
- can't be used for resebale workflows (yet)
- Windows and macOS based platforms are currently unsupported and won't work 