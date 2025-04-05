

# mavs.sh

This is a shell script to perform static analysis on mobile applications. Currently it only works for android apk files.
What makes this tool different from all the other tools that do this? My goal with this project is to actually exploit things.
Often you find static analysis tools point to things and say **VULNERABLE!** and the user is left to figure out why. Or worst its a 
false positive. 

This tool has two options currently:
  - -v verbose = Show me why you think its broken (useful for fixing and reporting)
  - -e exploit = Show me how to exploit this so called broken thing. Or show me how to manually check if it is indeed broken. I try
  provide actual commands that can be cut and pasted into the terminal verbatim to demonstrate risk.

## Required Dependencies
```
apkinfo       # sudo apt-get install apkinfo
d2j-dex2jar   # sudo apt-get install openjdk-7-jre
apktool       # https://ibotpeaches.github.io/Apktool/install/
```

## Usage mavs.sh
```
╕
 

Usage: mavs.sh [OPTIONS]

 Required:
  -f <apk>	Andorid APK file to decompile and run static analysis
 
 Options:
  -v 		Verbose, show affected files
  -e 		Show how to exploit finding
  -h 		Show this help

```
## Example Output
<img width="1035" alt="Screen Shot 2020-05-28 at 1 17 24 AM" src="https://user-images.githubusercontent.com/1679089/84467716-ccf1e000-ac31-11ea-9dd9-47a059dc4e33.gif">

## Current Security Checks

1. Insufficient Certificate Validation -- partial check
2. Application Logging
3. Backups Allowed
4. Debugging Enabled
5. Snapshot Allowed
6. Cleartext Allowed
7. Debugging Enabled
8. Hard codded *.pem files
9. App built with flutter
10. Provides examples on how to check app, device storage issues
