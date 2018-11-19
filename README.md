# README

This is the repository for my [faculty webpage](http://faculty.washington.edu/bmarwick/)

## Copyright

All content on these pages is in the [public domain](http://creativecommons.org/publicdomain/zero/1.0/)

## Site Details

* Pages mostly written [markdown](https://daringfireball.net/projects/markdown/)
* Theme and layout by [hugo-academic](https://github.com/gcushen/hugo-academic)
* Static site generation by [blogdown](https://bookdown.org/yihui/blogdown)
* Developed in the open on [GitHub](https://github.com/benmarwick)

## Things to keep in mind

* Edit pages, then `blogdown::build_site()`, then `git commit` and `git push`

* Deploy from my local copy directory to the UW server (bypassing github): `rsync -ravz public/* bmarwick@ovid.u.washington.edu:public_html` or use WinSCP. May also need to `chmod 755`
