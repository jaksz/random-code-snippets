# Inverting cloze cards in Anki

Use this code to swap the cloze question with the cloze answer on Anki cards:

```python
import re

input = open ('input.txt', 'r')
output = open('output.txt', 'a')

def conv_line(fl):
    result = re.sub(r'c1::(.*?)::(.*?)}}', r'c1::\2::\1}}', fl)
    return result

for line in input.readlines():
    line = conv_line(line)
    print line
```
