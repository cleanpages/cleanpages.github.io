# "Clean Pages" website  product version
## Build develop version site:
bundle exec jekyll serve

## Build product version site:
JEKYLL_ENV=production bundler exec jekyll build

## Deploy website:
rsync -anv --exclude={*.txt,*.yml,*.xml} _site/ /home/chao/git/website/
