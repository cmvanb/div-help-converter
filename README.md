# div-help-converter

Converts the standard div help file into a bunch of markdown which can be then parsed by mkdocs. Very much a work in progress

# Requirements

PHP: https://secure.php.net/downloads.php  
mkdocs: http://www.mkdocs.org/ 

# Running the program

Run the PHP conversion script:  
`php -f divdocs.php`  

Build the mkdocs website:  
`mkdocs build`  

Build and serve the mkdocs website locally (open 127.0.0.1:8000):  
`mkdocs serve`  
