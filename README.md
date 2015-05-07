# readme

This is the repository for my [faculty webpage](http://faculty.washington.edu/bmarwick/)

## Copyright

All content on these pages is in the [public domain](http://creativecommons.org/publicdomain/zero/1.0/)

## Site Details

* Pages mostly written [markdown](https://daringfireball.net/projects/markdown/)
* Theme and layout by [Hyde](http://hyde.getpoole.com/) & [Kieran Healy](http://kieranhealy.org/)
* Static site generation by [Jekyll](http://jekyllrb.com)
* Developed in the open on [GitHub](https://github.com/benmarwick)

## Things to keep in mind

* My `public_html` is in `/bmarwick` so I need to follow [these instructions](http://davidpots.com/blog/jekyll-github-pages-compass/) to get the CSS loading and internal links working
* When building the site locally I view it at `http://localhost:4000/bmarwick/index.html` and serve it with `jekyll serve --watch` so I don't have to rebuild for every edit, only need to refresh the browser.
* After working on the site locally, `jekyll build` then `git commit -am somemessage` then `git push` to update this github repor
* To copy to the UW server, note that github hides the `_site` directory, so we'll put that in another branch to send to the UW server:
```
# assuming we've already done jekyll build...
git checkout ovid # move to uw server branch
git checkout master -- _site # move dir over
mv _site/* . # move files from _site up one level
rmdir _site # delete _site
git add --all # add files to git
git commit -am "update ovid branch"
git push -u origin ovid # update github
```
Now we branch that is just the contents of _site, ready for the UW server to recieve. To deploy from github to UW server:
```
ssh bmarwick@ovid.u.washington.edu
cd public_html
git pull origin ovid
exit # exit ssh 
```


* To deploy from local to server (bypassing github): `rsync -ravz /home/two/mysite/_site/* bmarwick@ovid.u.washington.edu:public_html`

