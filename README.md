# snippets
Snippets to use with python

## Youtube Video Search
def ytload(term):
    term=term.replace(" ","+")
    page = requests.get('https://www.youtube.com/results?search_query=%s' %(term))
    txt=page.text
    print re.search(r'/watch\?v=(.*)',txt).group().split()[0][:-1]
