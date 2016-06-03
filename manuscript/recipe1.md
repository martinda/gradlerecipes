## Recipe 1: Creating an output file

The following code creates an output file with GNU Make:

```cmake
outputfile.txt:
  echo "text" >$@
```

Executing `make outputfile.txt` will create the file if it does not exist. Once the file exists, GNU Make will not longer try to create it. In this case, GNU Make does not track the file content, it only checks whether it exists or not.

The following code creates an output file with Gradle:

```groovy
task outputFileName() {
    def outputFile = new File('outputFile.txt')
    outputs.file outputFile
    doLast {
        println "Writing content to file ${outputFile.name}"
        outputFile.write("content\n")
    }
}
```