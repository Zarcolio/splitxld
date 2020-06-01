# Splitxld
Split an FQDN in parts and rearrange its parts

# Usage
```
usage: splitxld [-h] [-321] format

positional arguments:
  format              Each % plus number from 1 to 9 is replaced with the
                      corresponding domain level taken from the input (takes
                      vTLD such as co.uk into account). For example, if the
                      argument %3.%2.%1 is given and stdin supplies
                      sub5.sub4.sub3.example.co.uk then sub3.example.co.uk is
                      returned. The dots are free-form, any character can be
                      used.

optional arguments:
  -h, --help          show this help message and exit
  -321, --extract321  Separeate second (%2) and top level domain (%1), and the
                      remaining part (%3).
```
# Example
```
echo www.google.com | splitxld "%3 is the subdomain of %2.%1"
```
This results in:
```
www is the subdomain of google.com
```
