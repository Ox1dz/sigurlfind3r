# sigurlfind3r

[![release](https://img.shields.io/github/release/signedsecurity/sigurlfind3r?style=flat&color=0040ff)](https://github.com/signedsecurity/sigurlfind3r/releases) ![maintenance](https://img.shields.io/badge/maintained%3F-yes-0040ff.svg) [![open issues](https://img.shields.io/github/issues-raw/signedsecurity/sigurlfind3r.svg?style=flat&color=0040ff)](https://github.com/signedsecurity/sigurlfind3r/issues?q=is:issue+is:open) [![closed issues](https://img.shields.io/github/issues-closed-raw/signedsecurity/sigurlfind3r.svg?style=flat&color=0040ff)](https://github.com/signedsecurity/sigurlfind3r/issues?q=is:issue+is:closed) [![license](https://img.shields.io/badge/license-MIT-gray.svg?colorB=0040FF)](https://github.com/signedsecurity/sigurlfind3r/blob/master/LICENSE) [![twitter](https://img.shields.io/badge/twitter-@signedsecurity-0040ff.svg)](https://twitter.com/signedsecurity)

sigurlfind3r is a reconnaissance tool, it fetches URLs from **AlienVault's OTX**, **Common Crawl**, **URLScan**, **Github** and the **Wayback Machine**.

**DiSCLAIMER:** fetching urls from github is a bit slow.

## Usage

To display help message for sigurlfind3r use the `-h` flag:

```
$ sigurlfind3r -h

     _                  _  __ _           _
 ___(_) __ _ _   _ _ __| |/ _(_)_ __   __| | ___ _ __
/ __| |/ _` | | | | '__| | |_| | '_ \ / _` |/ _ \ '__|
\__ \ | (_| | |_| | |  | |  _| | | | | (_| |  __/ |
|___/_|\__, |\__,_|_|  |_|_| |_|_| |_|\__,_|\___|_| v1.0.0
       |___/

USAGE:
  sigurlfinder [OPTIONS]

OPTIONS:
  -d,  --domain            domain to fetch urls for
  -es, --exclude-sources   comma(,) separated list of sources to exclude
  -is, --include-subs      include subdomains' urls
  -ls, --list-sources      list all the available sources
  -nc, --no-color          no color mode
  -s,  --silent            silent mode: output urls only
  -us, --use-sources       comma(,) separated list of sources to use

```

## Installation

#### From Binary

You can download the pre-built binary for your platform from this repository's [releases](https://github.com/signedsecurity/sigurlfind3r/releases/) page, extract, then move it to your `$PATH`and you're ready to go.

#### From Source

sigurlfind3r requires **go1.14+** to install successfully. Run the following command to get the repo

```bash
▶ GO111MODULE=on go get -u -v github.com/signedsecurity/sigurlfind3r/cmd/sigurlfind3r
```

#### From Github

```bash
▶ git clone https://github.com/signedsecurity/sigurlfind3r.git
▶ cd sigurlfind3r/cmd/sigurlfind3r/
▶ go build; mv sigurlfind3r /usr/local/bin/
▶ sigurlfind3r -h
```

## Post Installation

sigurlfind3r will work after [installation](#installation). However, to configure sigurlfind3r to work with certain services - currently github - you will need to have setup API keys. The API keys are stored in the `$HOME/.config/sigurlfind3r/conf.yaml` file - created upon first run - and uses the YAML format. Multiple API keys can be specified for each of these services.

Example:

```yaml
version: 1.3.1
sources:
    - commoncrawl
    - github
    - otx
    - urlscan
    - wayback
keys:
    github:
        - d23a554bbc1aabb208c9acfbd2dd41ce7fc9db39
        - asdsd54bbc1aabb208c9acfbd2dd41ce7fc9db39
```

## Contribution

[Issues](https://github.com/signedsecurity/sigurlfind3r/issues) and [Pull Requests](https://github.com/signedsecurity/sigurlfind3r/pulls) are welcome!