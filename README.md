# snippets
Snippets to use with python

### #1: Youtube Video Search
```
def ytload(term):
    term=term.replace(" ","+")
    page = requests.get('https://www.youtube.com/results?search_query=%s' %(term))
    txt=page.text
    print re.search(r'/watch\?v=(.*)',txt).group().split()[0][:-1]
```
### #2: Colors and Erasing Lines
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
### #3: Updating written line
```
sys.stdout.write('\rComic.no:(%s)' %(index))
sys.stdout.flush()
```
### #4: lxml html example
```
page = requests.get('http://songs-tube.net/artist_letter.php?artist=%s' %(src[0].lower()))
tree = html.fromstring(page.content)
track = tree.xpath('/html/body/div[3]/div[3]/div[@class="songlist"]/a')
```
### #5: Fix that f**king unicode error example
```
stdscr.addstr(0,0,u'%s'.encode('utf_8') %(artlist[artno]))
```
### #6: Get video urls from a youtube playlist
```
def ytload(term):
    urls=[" "]
    page = requests.get(term)
    txt=page.text
    for i in re.findall(r'/watch\?v=(.*)',txt):
      url="https://youtube.com/watch?=%s" %(i[0:i.find('&amp')])
      if url not in urls:
        urls.append(url)
    print "%s videos found." %(len(urls)-1)
    print "\n".join(urls)
```
