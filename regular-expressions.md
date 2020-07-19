# Regular Expression

If you are going to use the regular expression functions often in your XPath
searches, you can register a namespace prefix once in the "global" namespace so
you do not need to use the namespaces= option.

Find all description elements that have a value containing the string "net",
ignoring case; i.e. would match "net", "Net", "NET", etc.

```python
from lxml import etree
etree.FunctionNamespace("http://exslt.org/regular-expressions").prefix = 're'

root = etree.fromstring(open("some-xml-file").read())
root.xpath('.//description[re:match(., "net", "i")]')
```

For more information on the regex extension library: http://exslt.org/regexp/.
