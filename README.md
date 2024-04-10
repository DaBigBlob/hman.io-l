# api.hman.io/l or 0x000.io/l
this is a very simple and fast link shortner (for my family, friends, projects maintainers, and reasonable people).   
this doesnt redirect. it directly responds with the data.   
it also preserves headers, methods, etc.

# examples
"https://api.hman.io/l/ma6s" responds with the data from "https://raw.githubusercontent.com/DaBigBlob/ms-store-arm64/main/allowARMv2.ps1"

# how to add your own url
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
        ...
        {
            "pseudo_path": "ma6s",
            "link": "https://raw.githubusercontent.com/DaBigBlob/ms-store-arm64/main/allowARMv2.ps1"
        },
        {
            "pseudo_path": "ypis",
            "link": "https://raw.githubusercontent.com/yt-dlp-archives/plugins/main/install_plugin"
        },
        {
            "pseudo_path": "REPLACE-WITH-YOUR-SHORT-PATH",
            "link": "REPLACE-WITH-YOUR-ACTUAL-URL"
        }
    ]
}
```
3. make a pull request

