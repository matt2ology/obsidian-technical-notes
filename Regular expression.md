---
alias: RegEx
---
# Regular expression

[RegEx Reference - regexr.com](https://regexr.com/)

`^` : the beginning of search string
`$` : the end of search string
often used together as `^()$` - `^(?P<album_id>[0-9]+)/$` generates pattern /music/album_id/

`()` is a group that will "unify" numbers/string, so 9001 is read as a whole and not 9-0-0-1