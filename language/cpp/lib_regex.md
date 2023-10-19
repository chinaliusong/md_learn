## 正则表达式
### C++11 regex
```C++
std::regex reg("<.*>.*</.*>");
bool ret = std::regex_match("<html>value</html>", reg);
assert(ret);

ret = std::regex_match("<header>value</header>", std::regex("<(.*)>value</\\1>"));
assert(ret);

std::cmatch m;
auto ret = std::regex_match("<xml>value</xml>", m, std::regex("<(.*)>(.*)</(\\1)>"));
```

```C++
1  std::regex reg("<(.*)>(.*)</(\\1)>");
2  std::cmatch m;
3  auto ret = std::regex_search("123<xml>value</xml>456", m, reg);
4  if (ret)
5  {
6      for (auto& elem : m)
7          std::cout << elem << std::endl;
8  }
9  
10  std::cout << "prefix:" << m.prefix() << std::endl;
11  std::cout << "suffix:" << m.suffix() << std::endl;
```

```C++
 1   std::regex reg("<(.*)>(.*)</(\\1)>");
 2   std::string content("123<xml>value</xml>456<widget>center</widget>hahaha<vertical>window</vertical>the end");
 3   std::smatch m;
 4   auto pos = content.cbegin();
 5   auto end = content.cend();
 6   for (; std::regex_search(pos, end, m, reg); pos = m.suffix().first)
 7   {
 8       std::cout << "----------------" << std::endl;
 9       std::cout << m.str() << std::endl;
10       std::cout << m.str(1) << std::endl;
11       std::cout << m.str(2) << std::endl;
12       std::cout << m.str(3) << std::endl;
13   }
```
#### 分词
```C++
1   std::string mail("123@qq.vip.com,456@gmail.com,789@163.com,abcd@my.com");
2   std::regex reg(",");
3   std::sregex_token_iterator pos(mail.begin(), mail.end(), reg, -1);
4   decltype(pos) end;
5   for (; pos != end; ++pos)
6   {
7       std::cout << pos->str() << std::endl;
8   }
```
#### 替换
```C++
1　　char data[] = "he...ll..o, worl..d!";
2　　std::regex reg("\\.");
3　　// output: hello, world!
4　　std::cout << std::regex_replace(data, reg, "");


1　　char data[] = "001-Neo,002-Lucia";
2　　std::regex reg("(\\d+)-(\\w+)");
3　　// output: 001 name=Neo,002 name=Lucia
4　　std::cout << std::regex_replace(data, reg, "$1 name=$2");
```