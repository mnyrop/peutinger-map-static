# peutinger-map-static

## results 

- [manifest](https://mnyrop.github.io/peutinger-map-static/base/manifest.json)
- [sample static image derivative](https://mnyrop.github.io/peutinger-map-static/img/base-1/21504,1024,1024,1024/512,/0/default.jpg)
- [viewer with manifest loaded](https://dss.hosting.nyu.edu/viewpoint/mirador/#manifests[]=https%3A%2F%2Fmnyrop.github.io%2Fpeutinger-map-static%2Fbase%2Fmanifest.json&theme=dark&thumbs=off&view=single&workspacecontrols=false)

## contents

- `docs` — published [IIIF JSON-LD files](https://github.com/mnyrop/peutinger-map-static/tree/main/docs/base) and [static, pregenerated image derivatives](https://github.com/mnyrop/peutinger-map-static/tree/main/docs/img/base-1)  
- `source` — source data files (in this case, one image)  
- `Rakefile` — code entry point for rake task & iiif builder; includes preliminary config vars
- `.env` — .gitignored file; can be added locally to set secret ENV variables, e.g., AWS credentials

## run locally

### prerequisites
- git
- imagemagick
- ruby via rvm

### steps
1. clone repo & cd into it
2. install ruby gems with `bundle install`
3. build the static IIIF resources with `bundle exec rake build`
