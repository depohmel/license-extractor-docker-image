# Docker file for license-extractor

this is a docker file for https://www.npmjs.com/package/license-extractor

If you have to exctarct linceses (text including) for all you submodules, libs, modules etc  this image might help you.

## How to use

Let's imagine you are in golang project.

```
ls -lh ./
total 172
drwxr-xr-x  3 root root  4096 May 16 20:47 bin
drwxrwxr-x  4 root root  4096 May 15 11:38 cmd
drwxr-xr-x  5 root root  4096 May 16 21:28 dist
drwxrwxr-x  5 root root  4096 May 15 17:50 docs
-rw-rw-r--  1 root root     0 May 16 17:47 foo
-rw-rw-r--  1 root root  1268 May 15 11:38 glide.yaml
drwxrwxr-x  2 root root  4096 May 15 11:38 graphic
-rwxrwxr-x  1 root root 11358 May 15 11:38 LICENSE
drwxrwxr-x 16 root root  4096 May 15 11:38 pkg
drwxr-xr-x  8 root root  4096 May 16 20:48 vendor
```

and you want to get licneses for everypackage in vendor folder

```
docker run --rm -t -v $(pwd):/repo depohmel/license-extractor:latest --source /repo/vendor
```

this cmd will start printing loooong list of licenses
example: 
```
--------------------------------------------------------------------------------
 repo vendor cloud.google.com go LICENSE (/repo/vendor/cloud.google.com/go/LICENSE)
--------------------------------------------------------------------------------

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

```

for more docs please go to https://www.npmjs.com/package/license-extractor




