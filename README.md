# "Clean Pages" website  product version
## Build develop version site:
bundle exec jekyll serve --incremental

## Build product version site:
JEKYLL_ENV=production bundler exec jekyll build

## Deploy website:
### Dry run
with Archive, Verbose, Update, Checksum, Ignore directory timestamp, and sync exclude pattern:
rsync -avucn --omit-dir-times --exclude={*.txt,*.yml,*.xml,*.gemspec} _site/ /home/chao/git/website/

### Real run:
rsync -avuc --omit-dir-times --exclude={*.txt,*.yml,*.xml,*.gemspec} _site/ /home/chao/git/website/

Note: After changed post markdown file name, and deployed (rsync) into "website", don't forget to manually delete the folder that has been generated with the old post file name.
