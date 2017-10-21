The open-source citizen commit message collection
=================================================

Collection of well crafted and informative commit messages used when
updating a project to follow the best practices.

> I created this collection of commit messages because I too often
> find myself browsing history of projects I worked on to copy-paste
> content of messages.
>
> -- <cite>@jcfr on Saturday, October 21, 2017</cite>

Contributions are welcome.

Table of Contents
=================

   * [The open-source citizen commit message collection](#the-open-source-citizen-commit-message-collection)
   * [Python](#python)
      * [flake8](#flake8)

<!--
*Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)*
-->

[![][cc-img]][cc]

This work is licensed under a [Creative Commons Attribution 4.0 International License][cc].

[cc]: http://creativecommons.org/licenses/by/4.0/
[cc-img]: https://i.creativecommons.org/l/by/4.0/80x15.png


# Python

## flake8

```
STYLE: Add .flake8 configuration to support python script validation

Flake8 is a python source checker.

The initial configuration file adds exceptions for all errors, it will
iteratively be updated as the code is improved.

After installing flake8 with `pip install flake8`, the following shell
script was used to craft the list of exceptions:

  IFS=$'\n'
  for line in $(flake8 . | cut -d":" -f4 | sort | uniq)
  do
     # Remove leading space
     line=$(echo $line | sed -e 's/^[ \t]*//')
     # Extract error code
     code=$(echo $line | cut -d" " -f1)
     echo "    # $line"
     echo "    $code,"
  done

Internally flake8 is wrapper around these tools:

* PyFlakes: analyzes programs and detects various errors. It works by
  parsing the source file, not importing it, so it is safe to use on
  modules with side effects. It’s also much faster.

* pycodestyle: a tool to check your Python code against some of the
  style conventions in PEP 8 (the style guide for python code).
  See https://www.python.org/dev/peps/pep-0008/

* Ned Batchelder’s McCabe script: check McCabe (or cyclomatic) complexity.
  See https://en.wikipedia.org/wiki/Cyclomatic_complexity.

To learn more about flake8. See http://flake8.pycqa.org/en/latest/
```

