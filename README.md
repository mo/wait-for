# wait-for

wait-for is a Python script that runs a command every N seconds until the
command prints something new, prints a specific string or returns a given exit
code.

```bash
$ # Suppose OpenSSL (or similar) has announced that they will publish a new
$ # security fix today and you want a notification when they publish the details.
$ CHANGELOG="https://www.openssl.org/news/changelog.txt"
$ wait-for --stdout-change "curl -s $CHANGELOG" ; notify-send "It's published"

$ # Suppose you have a scruffy old Jenkins server, and you want to wait for the
$ # next successful build and then deploy that to some a staging environment.
$ URL="http://jenkins.ecorp.com/job/SOME_JOB_NAME/lastSuccessfulBuild/api/json"
$ wait-for --stdout-change "curl -s $URL | jq .number" ; deploy-latest-successful
```

## License

The MIT License (MIT)

Copyright (c) 2016 molsson

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
