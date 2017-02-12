My JSFiddle files are backed up to this github repo
==





How I backed up my fiddles.

Step 0: Bookmark all jsfiddle urls (Yeah, I know, it sucks).

Step 1: Export bookmarks from google chrome (bookmark manager, click Organise, Export).

Step 2: Generate a urls file.

    grep -oh "https://jsfiddle.net/.*/" bookmarks.html | awk '{print (}' | grep -v "user\/dashboard" | sed 's/\"//'  | sed 's/jsfiddle.net/fiddle.jshell.net/' | awk '{print ( "show/light/"}')) > urls

Step 3: Set wget's User-Agent and download from urls list.

    wget --header="User-Agent: Mozilla/5.0 (Windows NT 6.0) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.97 Safari/537.11" --header="Referer: https://jsfiddle.net/"  -i ../urls
