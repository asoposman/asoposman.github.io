---
layout: single
title: 'How to parse Greek characters using python'
description: 'This blog post provides a python script which parses Greek characters in a file.'
date: 2021-11-15
classes: wide
comments: false
tags:
  - greek characters
  - python
--- 

<p style="text-align:justify;">
In this guide I provide a python script for parsing Greek characters which are included in files in the following format:
</p>

> =CE=91=CE=A1=CE=91=CE=9C=CE=A0=CE=91= =CE=A4=CE=96=CE=97 =CE=A3=CE=BF=CF=86=CE=AF=CE=B1

<p style="text-align:justify;">
Normally, spaces in such files are depicted as <i>\x00\x00\x00=</i> or <i>\x00\x00=</i> or <i>\x00</i>, so I have taken this into consideration in the script.<br />    
This may be the case in several applications like dovecot, postfix etc, which save data in such formats.
</p>

<p style="text-align:justify;">
As a result, the final python script is the following:
</p>


```python

mail_file = open("parse_greek_chars.txt", "r", encoding="ISO-8859-1")
mail = mail_file.read()
mail=mail.replace('\n','')
mail=mail.replace('\x00\x00\x00=', '')
#mail=mail.replace('\x00\x00=', '')

mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x006', 'Ά')
mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x008', 'Έ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x009', 'Ή')
mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x00A', 'Ί')
mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x00C', 'Ό')
mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x00E', 'Ύ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x008\x00F', 'Ώ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x001', 'Α')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x002', 'Β')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x003', 'Γ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x004', 'Δ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x005', 'Ε')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x006', 'Ζ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x007', 'Η')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x008', 'Θ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x009', 'Ι')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x00A', 'Κ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x00B', 'Λ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x00C', 'Μ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x00D', 'Ν')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x00E', 'Ξ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x009\x00F', 'Ο')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x000', 'Π')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x001', 'Ρ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x003', 'Σ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x004', 'Τ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x005', 'Υ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x006', 'Φ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x007', 'Χ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x008', 'Ψ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x009', 'Ω')

mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x001', 'α')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x002', 'β')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x003', 'γ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x004', 'δ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x005', 'ε')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x006', 'ζ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x007', 'η')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x008', 'θ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x009', 'ι')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x00A', 'κ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x00B', 'λ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x00C', 'μ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x00D', 'ν')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x00E', 'ξ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00B\x00F', 'ο')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x000', 'π')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x001', 'ρ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x002', 'ς')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x003', 'σ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x004', 'τ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x005', 'υ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x006', 'φ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x007', 'χ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x008', 'ψ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x009', 'ω')

mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x00C', 'ά')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x00D', 'έ')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x00E', 'ή')
mail=mail.replace('\x00=\x00C\x00E\x00=\x00A\x00F', 'ί')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x00C', 'ό')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x00D', 'ύ')
mail=mail.replace('\x00=\x00C\x00F\x00=\x008\x00E', 'ώ')

mail=mail.replace('\x00', '')
mail=mail.replace('=', '')

with open('parse_greek_chars.html', "w", encoding="utf-8") as newmail:
    newmail.write(mail)

mail_file.close()    
```
<p style="text-align:justify;">
Feel free to modify the script if need be.
</p>

