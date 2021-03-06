# Confirm

A simple tool for scripted confirmation.  Returns zero if confirmed, non-zero otherwise.

```shell
$ confirm "Echo something?" -a 3 && echo something
Echo something? [y/n]: 
Echo something? [y/n]: 
Echo something? [y/n]: y
something
```

`confirm --help` output:

```
confirm 0.1.0
Get user confirmation

USAGE:
    confirm [FLAGS] [OPTIONS] [PROMPT]

FLAGS:
    -f, --full-words    
            Require explicit "yes" or "no", not single letters.
            
            Cannot be used with --no-enter.
    -h, --help          
            Prints help information

        --no-enter      
            Don't require newlines
            
            Read the character on the terminal as it's typed, without waiting for the user to hit enter/return.
    -V, --version       
            Prints version information


OPTIONS:
    -a, --ask-count <ask-count>    
            Number of times to ask
            
            Number of total times a question should be asked.  Use 0 for infinite retries. [default: 3]
    -d, --default <default>        
            Choose a default answer
            
            If no default is chosen, and the user supplies an empty answer, then a retry is triggered.  Otherwise, the
            default is used on an empty answer. If the retry count has been hit, then the process assumes a negative
            response and exits 1. Using the keyword "retry" is identical to omitting the option. [default: retry]

ARGS:
    <PROMPT>    
            The prompt to display
            
            Prompt of "Continue?" will become "Continue? [y/n]: ".  Options are added and highlighted based on given
            settings.  Original message will NEVER be modified. [default: Continue?]
```
