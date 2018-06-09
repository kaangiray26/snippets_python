# snippets
Snippets to use with python

### Youtube Video Search
```
def ytload(term):
    term=term.replace(" ","+")
    page = requests.get('https://www.youtube.com/results?search_query=%s' %(term))
    txt=page.text
    print re.search(r'/watch\?v=(.*)',txt).group().split()[0][:-1]
```
### Colors and Erasing Lines
```
class colors:
    HEADER = '\033[95m'
    blue = '\033[94m'
    green = '\033[92m'
    yellow = '\033[93m'
    red = '\033[91m'
    end = '\033[0m'
    bold = '\033[1m'
    UNDERLINE = '\033[4m'
print color.red + "hello" + color.end
```
```
ERASE_LINE = '\x1b[1J'
ERASE_ALL = '\x1b[g'
GO_HOME = '\x1b[H'
SCROLL = '\x1b[1000M'
os.system("clear && printf '\e[3J'")
```
