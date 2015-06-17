## Twitter stream recorder

**Outputs a twitter stream to STDOUT and/or log files, using the streaming API**  

* Optionally uses the REST API to prepend prior tweets to the start of the output.  
* Optionally reconnects if the stream is disconnected.  
* Optionally uses the REST API to fill in the gap whilst the stream was disconnected.  

### Usage:

    twitter-stream-recorder [options]

### Options:
* -f CONFIGFILE  
  Use CONFIG_FILE for API authorisation details,  
  and to store state between sessions.  
  Will not overwrite an existing file for new authorisations.  
  If the file does not exist, the user must  
  interactively authorise the application (enter a PIN on STDIN).  
  Defaults to ~/.twitter-stream-recorder
* -n  
  Non-interactive mode.  
  Fail if interactive authorisation is required.
* -r  
  Restart stream connection if it fails.
* -g  
  Use the REST API to fill any gaps between stream connections.  
  Implies: -r.
* -p INTEGER  
  Prepend up to this many tweets to the output (using the REST API),  
  up to the end of the previous session, if any.  
  Defaults to 0
* -v  
  Verbose mode
* -t  
  Timestamp verbose and diagnostic output
* -l DIRECTORY  
  Write stream to files in DIRECTORY.  
  This will output one log file per day with using filenames of  
  the form: twitter-stream-ID-NAME.YYYY-MM-DD.log  
  Requires File::Write::Rotate to be installed.
* -s
  Do not write to STDOUT  
  This is useful when using -l to log to files.
* -h  
  Show usage

### URLs:
* This project is hosted at: https://github.com/JGRennison/twitter-stream-recorder  

### Dependencies:
* perl  
  * JSON  
  * AnyEvent  
  * AnyEvent::Twitter 0.63  
  * AnyEvent::Twitter::Stream  
  * Getopt::Std  
  * File::Slurp  
  * File::HomeDir  
  * String::Numeric  
  * DateTime  
  * DateTime::HiRes  
  * Memoize  
  * Guard  
  * File::Write::Rotate [optional]  
  * File::Path [optional]  

### License:
GPLv2
