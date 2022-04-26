# Back-End-Internship-Task

This is a Back-end task for your internship at Forte Digital. To check your Back-end skills please complete a task specified in this document and send us zipped repo to an address you have received in the email. Before zipping make sure you will send us only source code, not executables. 

Your task is to create a command-line interface (CLI) application written in C# which will download a file from a given URL using HTTP, parse it and write to  standard output result of one of two commands: 
`count` or `max-age`. 

## Count command

`interns.exe count <url> [ --age-gt | --age-lt age]` 
This command counts number of interns satisifing condition and writes it to standard output. 
Options: 
- `--age-gt <age>` - counts interns where age is greater than `<age>`, where `<age>` is an integer
- `--age-lt <age>` - counts interns where age is less than `<age>`, where `<age>` is an integer


For instance:
`interns.exe count https://fortedigital.github.io/Back-End-Internship-Task/interns.json`
should write to standard output: `5`

`interns.exe count https://fortedigital.github.io/Back-End-Internship-Task/interns.json --age-gt 22`
should write to standard output: `2`
## Max age command

`interns.exe max-age <url>`

This command writes a maximum age of an intern to standard output.  

For instance:
`interns.exe max-age https://fortedigital.github.io/Back-End-Internship-Task/interns.json`
should write to standard output: `24`

## Download  & parse file 

The file contains a list of interns in three different formats: JSON, CSV, and zip archive with a CSV file. Intern data model consists of following properties:

- id: integer,
- age:  integer,
- name: string,
- email: string,
- internshipStart: date with time,
- internshipEnd: date with time.

You should determine file type based on content type. It can be JSON, CSV, or zip archive with CSV inside. Examples of files are accessible from the following URLs:
- https://fortedigital.github.io/Back-End-Internship-Task/interns.json
- https://fortedigital.github.io/Back-End-Internship-Task/interns.csv
- https://fortedigital.github.io/Back-End-Internship-Task/interns.zip


## Errors
When the application will not be able to get a file it should write to standard output:
`Error: Cannot get file.`

When an application will not able to process a file write to standard output:
`Error: Cannot process the file.`


When an application will not able to parse command write to standard output:
`Error: Invalid command.`

## Remarks
Keep in mind that you might need to add support for other commands or filter options in the future. Making sure your code is extensible will be a plus.

You are free to use external packages for instance from nuget.org. 

Try not to over-engineer this task. Focus on functionality rather than input validation.  