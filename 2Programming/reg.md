正则练习
https://alf.nu/RegexGolf?world=regex&level=r00

# 匹配findall
```python
import re
# 给定文本
text = "请问如何写一个普通的正则表达式？请问怎么使用python3实现正则表达式？"
# 提前编译正则表达式
# 匹配数字
regex = r'\w'
# 匹配任意字
# regex = '请问.'
# 从字符串的最开始进行匹配
# 脱字符
# regex = '^请问.'
regex = re.compile(regex)
result = re.findall(regex, text)
print(result)
```

# AC自动机
一次遍历，匹配多个规则
pip install esmre
```python
import esm
# 词库
keywords = ["保罗", "小卡", "贝弗利"]
# 连续文本
text = "NBA季后赛西部决赛，快船与太阳移师洛杉矶展开了他们系列赛第三场较量，上一场太阳凭借艾顿的空接绝杀惊险胜出，此役保罗火线复出"


# 实例化AC自动机
index = esm.Index()
# 将词库中的词送入index实例
for keyword in keywords:
  index.enter(keyword)
  index.fix()
# 针对连续文本进行匹配
result = index.query(text)
print(result)
```
