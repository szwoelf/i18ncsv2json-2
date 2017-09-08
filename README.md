i18ncsv2json
============

i18n csv file to json convetor.

Expect one csv file `tools.csv`, with following structure:

key   | en         | de 
------|------------|------------
about | about here | etwa hier
home  | homepage   | Startseite 

Execute following command:

    i18ncsv2json tools.csv

Then will generate 2 files, one is `tools.en.json`:

    {
      "about": "about here",
      "home": "homepage"
    }

And one is `tools.de.json`:

    {
      "about": "etwa hier",
      "home": "Startseite"
    }

### Encoding
 
 It is possible to choose the encodings (for source csv files and output json files). This can typically be usefull when managing the csv files via excel which by default saves the file in windows specific encoding and not utf-8. Default output encoding is utf8.
 
 Example command to use read csv file with Windows encoding and output it in utf16 :
 
     i18ncsv2json directory -r latin1 -w utf16
 

Usage
-----

    Usage: i18ncsv2json [options] <file ...>

    Options:

      -h, --help               output usage information
      -V, --version            output the version number
      -p, --path [value]       output path
      -d, --delimeter [value]  delimeter between filename and lang
      -t, --transpose          transpose input csv file
      -r, --readEncoding [value]    encoding to use to read files
      -w, --writeEncoding [value]   encoding to use to write files
