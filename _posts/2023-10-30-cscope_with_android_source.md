---
title : "cscope with android source"
excerpt : "generate android cscope db"

categories:
   - Blog
tags:
   - Blog
---

- generate android source


```
#!/bin/bash
echo "Listing Android files ..."
rm -f all.files
rm -f cscope.files
find \
        "./frameworks/" \
        "./packages/" \
        "./hardware/" \
        -type f \( -name "*.java" -o -name "*.c" -o -name "*.cpp" -o -name "*.h" -o -name "*.mk" \) \
        -print \
        -exec bash -c 'ls "$0" >> all.files' {} \;

echo "Done"
cat all.files | grep -Ev "tests" > cscope.files
time cscope -bqkR
```
