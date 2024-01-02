# alfred-to-memos
把那些每日灵感、碎碎念，随心打开alfred，一键直达obsidian的memos日记插件里。
实现日记本地化，完全可以拥有属于自己的数字资产了！#obsidian  #alfred  #memos
## 第一步 用chatGPT写一段段码
大意是在memos指定文件夹下，按时间创建今日日记文件，如果已存在，则在文件内续写；
- 代码如下：
```bash
#!/bin/bash

# 获取当前日期（年-月-日）和时间（小时:分钟）
current_date=$(date '+%Y-%m-%d')
current_time=$(date '+%H:%M')

# 设置文件名为当前日期，并添加.md后缀
file_name="${current_date}.md"

# 设置文件的完整路径为自己obsdian memos日记的位置
file_path="/Users/DRLer/Documents/kevinY/日记/${file_name}"

# 输入要添加的文字
# read -p "请输入要添加的文字: " input_text

# 在文件的开头添加时间和输入的文字，然后追加到文件
echo -e "- ${current_time} {query}\n$(cat $file_path)" > $file_path
echo "已将文字追加到文件 ${file_name}"

```
其中，obsdian memos日记的位置需要自定义；
## 第二步 放入alfred中，设置如下：
<img width="494" alt="image 3" src="https://github.com/yidianhongxin/alfred-to-memos/assets/11401362/1a1a3386-5ec4-4ec9-89d7-5e25553dfc4d">
<img width="474" alt="image 2" src="https://github.com/yidianhongxin/alfred-to-memos/assets/11401362/0a83be0f-4fc0-4630-a4e5-08cb4658367c">
<img width="794" alt="image" src="https://github.com/yidianhongxin/alfred-to-memos/assets/11401362/6b650846-8fb8-4384-a38d-0c039d38d60e">

## 第三步 Obsidian APP里需要安装memos第三方软件
<img width="634" alt="image 4" src="https://github.com/yidianhongxin/alfred-to-memos/assets/11401362/0a2c4e7f-cb3c-497b-aa67-be86b38da241">

## 最终效果
<img width="598" alt="image 5" src="https://github.com/yidianhongxin/alfred-to-memos/assets/11401362/b2a74a1f-9740-4613-9af8-8b54958413b7">
<img width="869" alt="image 6" src="https://github.com/yidianhongxin/alfred-to-memos/assets/11401362/0d5ccbc4-193f-4d1c-867b-5c57ed24511c">
