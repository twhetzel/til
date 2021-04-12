# Shell Script to Run Python Script

## Description
Using a shell script to run a Python script can be useful when using CI/CD systems where the commands 
to run the script are on one server (e.g. server where Bamboo is hosted) and the script runs
on another server. 

### Example Shell Script to Run Python script
```
#!/bin/bash

helpFunction()
{
   echo ""
   echo "Usage: $0 -c cfg_file -i input_directory -j output_directory -u user_file"
   echo ""
   echo "Parameter descriptions:"
   echo -e "\t-i Input file directory"
   echo -e "\t-j Output file directory"
   echo -e "\t-c Config file"
   echo -e "\t-u User input file"
   exit 1 # Exit script after printing help
}

while getopts "i:j:c:u:h" opt
do
   case "$opt" in
      i ) input_directory="$OPTARG" ;;
      j ) output_directory="$OPTARG" ;;
      c ) cfg_file="$OPTARG" ;;
      u ) user_file="$OPTARG" ;;
      h ) helpFunction ;; # Print helpFunction in case parameter is non-existent
   esac
done

# Set default values
INPUTDIR="./data/input/"
OUTPUTDIR="./data/output/"
CFG_FILE="cfg_labvid.ini"
USER_FILE="Users - Sheet1.csv"

# Print helpFunction in case parameters are empty
if [ -z "$input_directory:-$INPUTDIR" ] || 
[ -z "$output_directory:-$OUTPUTDIR" ] || 
[ -z "$cfg_file:-$CFG_FILE" ] || 
[ -z "$user_file:-$USER_FILE" ] || 
then
   echo "See help using -h for script parameter options.";
fi

# Run script with config, canonical data input files, and input/output data directories.
PythonCommand="python main.py 
--cfg_file ${cfg_file:-$CFG_FILE} 
--input_directory ${input_directory:-$INPUTDIR} 
--output_directory ${output_directory:-$OUTPUTDIR} 
--user_file ${user_file:-$USER_FILE} 

${PythonCommand}
```
