# pot-translate

use google to translate .pot file（free）



## 安装两个模块

popy                ：用于解析
pygoogletranslation ：用于翻译

## 需要修改popy的PoFile的一处代码

from popy.po_file import PoFile
ctrl 单击 PoFile，修改 write_messages部分
由

```
def write_messages(self):
  content = ""
```

改为

```
def write_messages(self,mes):
  self.messages = mes
  content = ""
```

完整如下所示：

```
def write_messages(self,mes):
    self.messages = mes
    content = ""
    for message in self.messages:
        content += message.__str__() + 'n'
    self._write_file(content)
```

## 直接使用py文件即可

