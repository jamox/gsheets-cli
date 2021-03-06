## CLI for appending rows to Google Spreadsheets

### How to use

After building shaded minified jar (`mvn package`) run it like
```shell
$ java -Xmx32m -client -jar target/gsheets-cli-1.0-SNAPSHOT.jar <options>
```

Service account needs to be created at: https://console.developers.google.com/apis/credentials - select to use the p12 file

`--serviceAccountId`
Email address of the service account

`--p12Path`
Path to the .p12 credential file (you get it when creating the service
account

`--documentName`
Human readable name of the spreadsheet

`--sheetName`
Human readable name of the sheet of the spreadsheet

`--values`
Key=Value separated by the `--separator`  corresponding keys must be
found on the first row of the sheet.
e.g `"Temp=20.2,Date=11/15/2015 12:20,Humidity=40.11"

`--separator ","`
Characted used for separating values for the `--values`, `--file` and `--keys`

`--file`
File to read (basically weakly parsed cvsish data.

`--keys`
Keys in respective ordef to the fields in the `--file`

Not that the `--values` and `--file` cannot be used simultaneously.
