# peutinger-map-static

Fully static, IIIF Level 0 represesentation of Peutinger Map. Resources currently published to GitHub Pages; Can instead be synched to S3 storage or deployed via FTP to NYU Web Hosting Account.

## Results 

- [Manifest](https://nyu-dss.github.io/peutinger-map-static/base/manifest.json)
- [Sample static image derivative](https://nyu-dss.github.io/peutinger-map-static/img/base-1/21504,1024,1024,1024/512,/0/default.jpg)
- [Viewer with manifest loaded](https://dss.hosting.nyu.edu/viewpoint/mirador/#manifests[]=https%3A%2F%2Fnyu-dss.github.io%2Fpeutinger-map-static%2Fbase%2Fmanifest.json&theme=dark&thumbs=off&view=single&workspacecontrols=false)

## Contents

- `docs` — published [IIIF JSON-LD files](https://github.com/nyu-dss/peutinger-map-static/tree/main/docs/base) and [static, pregenerated image derivatives](https://github.com/nyu-dss/peutinger-map-static/tree/main/docs/img/base-1)  
- `source` — source data files (in this case, one image)  
- `Rakefile` — code entry point for rake task & iiif builder; includes preliminary config vars
- `.env` — .gitignored file; can be added locally to set secret ENV variables, e.g., AWS credentials

## Run locally

### Prerequisites
- git
- imagemagick
- ruby via rvm

### Steps
1. Clone repo & cd into it
2. Install Ruby gems with `bundle install`
3. Build the static IIIF resources with `bundle exec rake build`
