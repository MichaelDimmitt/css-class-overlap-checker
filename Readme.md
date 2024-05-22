## css-class-overlap-checker

1. compare css files
    0. input
        - 2 files required as input. 
    1. using grep 
        - get all .classes 
           - trimmed to just the .class part.
           - put the list from file 1 in a temp file
           - put the list from file 2 in another temp file
           - determine which file has less classes by counting number of lines in the file
           - if one file is empty it will end program and say no classes in css file.

    2.  use the file with less classes to 
        - loop over each line
            - grep that .class on the other temp file
            - if that class exists append it to temp file 3
    3. if temp file 3 exists 
        - move it to resultsfile
        - delete temp files
        - notify user done and outcome
    4. if temp file 3 does not exist
        - delete temp files
        - notify user done and outcome

2. futher considerations
    0. common html tags
    1. media query intersection
