# api.hman.io/l or a.hman.io/l
this is a very fast and fancy "link shortner" (for my family, friends, projects maintainers, and reasonable people).   
it directly responds with the data or redirects deepending on `type` [see below].      
it also preserves headers, methods, etc if directly responding with data.   

# examples
- "https://a.hman.io/l/ma6s" responds with the data from "https://raw.githubusercontent.com/DaBigBlob/ms-store-arm64/main/allowARMv2.ps1"   
- "https://a.hman.io/l/favsong" redirects to "https://www.youtube.com/watch?v=sVz3_9g4LlQ" (my favourite song)

# l_list.json structure
```ts
{
    "list": [       // list of entries
        {   // an entry
            "type:": "pipe",        // is either "pipe" or "redir" exactly; is string obviously
            "pseudo_path": "goog",  // is string; the part that comes after /l/ in https://a.hman.io/l/
            "link": "https://www.google.com" // is string; the actual url to redirect to
        },
        ... // more entries
    ]
}
```

# how to add your own url
> NOTE: you can also just ask me and i'll do the following for you

1. be family or friend or project maintainer or just a resonable person
2. clone repo and get into it
```bash
git clone https://github.com/DaBigBlob/hman.io-l.git
cd hman.io-l
```
3. add a new entry in l_list.json, under list, like:
```json
{
    "list": [
        {
            "type:": "pipe",
            "pseudo_path": "ma6s",
            "link": "https://raw.githubusercontent.com/DaBigBlob/ms-store-arm64/main/allowARMv2.ps1"
        },
        {
            "type:": "pipe",
            "pseudo_path": "ypis",
            "link": "https://raw.githubusercontent.com/yt-dlp-archives/plugins/main/install_plugin"
        },
        {
            "type:": "redir",
            "pseudo_path": "favsong",
            "link": "https://www.youtube.com/watch?v=sVz3_9g4LlQ"
        },
        {
            "type:": "REPLACE-WITH-KIND",
            "pseudo_path": "REPLACE-WITH-YOUR-SHORT-PATH",
            "link": "REPLACE-WITH-YOUR-ACTUAL-URL"
        }
    ]
}
```
3. make a pull request

> ADDITIONAL TECHNICAL NOTE: the redirects/pipes take effect 5mins after this repository is updated. this is to keep down costs.