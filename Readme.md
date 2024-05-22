## css-class-overlap-checker

## Structure:
1. directory: example_css_files
    - tachyons has a simple enough css file to be in this directory.
    - others will be custom small css files
    - if I think of another simple css file it will go in.
2. script

## Plan: 
1. compare css files
    1. input
        - 2 files required as input. 
    2. using grep 
        - get all .classes (unminified)
           - trimmed to just the .class part.
           - put the list from file 1 in a temp file
           - put the list from file 2 in another temp file
           - determine which file has less classes by counting number of lines in the file
           - if one file is empty it will end program and say no classes in css file.
        - get all .classes (minified)
           - each .class discovery will be added to a newline in tempfile 1

    3.  use the file with less classes to 
        - loop over each line
            - grep that .class on the other temp file
            - if that class exists append it to temp file 3
    4. if temp file 3 exists 
        - move it to resultsfile
        - delete temp files
        - notify user done and outcome
    5. if temp file 3 does not exist
        - delete temp files
        - notify user done and outcome

2. futher considerations
    1. common html tags
    2. media query intersection
    3. this probably already exists but whatever, easy to build.
3. The secret plan.
    1. write it in 10 lines of bash
    2. give it to https://github.com/menketechnologies to re-write it in rust 🙂

## Some thoughts:
```bash
# I do not like the tr, can grep do the newline for me on minified capture?
grep -ohE "([\.]).*\{" example_css_files/tachyons.min.css | tr "{" "\n" 
 
# I do not like the tr, causes newlines if same tr used on unminified. I would like to limit conditionals for code golf.
grep -oE "([\.]).*\{" example_css_files/tachyons.css | tr "{" "\n" `

# I do not like green eggs and ham.
# I do not like them sam I am.
```
