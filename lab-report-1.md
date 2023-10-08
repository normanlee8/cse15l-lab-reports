# Lab Report 1 - Norman Lee

## cd command

![cdcode](Screenshot 2023-10-02 at 1.47.58 PM.png)

* Using cd with no arguments returned nothing because there was no directory to change to
* Using cd with a path to the *messages* directory changed the working directory to the *messages* directory
* Using cd with a path to the *fr.txt* file returned an error because cd is used to change directories and *fr.txt* is not a directory, it is a file.

## ls command

![lscode](Screenshot 2023-10-02 at 1.48.15 PM.png)

* Using ls with no arguments listed the files and directories in the current working directory, which was the *home* directory
* Using ls with a path to the *messages* directory listed the files within that directory
* Using ls with a path to the *fr.txt* file returned the path to that file because that is the location of the file

## cat command

![lscode](Screenshot 2023-10-02 at 1.48.25 PM.png)

* Using cat with no arguments returned an empty line, which required exiting out of that command line because there was no content to print out nor a path to a file
* Using cat with a path to the *messages* directory returned the path and that it was a directory because cat is used to print contents of files, not directories
* Using cat with a path to the *fr.txt* file printed "Bonjour le monde" because that was the content of the file
