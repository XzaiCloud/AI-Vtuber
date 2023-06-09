# AI Vtuber

AI Vtuber是一个由ChatterBot驱动的虚拟主播，可以在Bilibili直播中与观众实时互动。它使用自然语言处理和文本转语音技术生成对观众问题的回答。

交流群：[745682833](https://jq.qq.com/?_wv=1027&k=IO1usMMj)

### 运行环境
- Python 3.6+
- Windows操作系统

### 安装依赖
在命令行中使用以下命令安装所需库：
```bash
pip install ChatterBot bilibili-api-python edge-tts
```
此外，还需要[下载并安装mpv](https://mpv.io/installation/)。在Windows操作系统上，也需要将 `mpv.exe` 添加到环境变量中。对于其他操作系统，请将其路径添加到系统 `PATH` 环境变量中。

如果ChatterBot安装报错，请前往 https://github.com/RaSan147/ChatterBot_update 安装新版本。下载下来输入`python setup.py install`即可

### 配置
1. 打开 `main.py` 文件并修改 `database_uri` 变量的值以指定用于存储对话历史的SQLite数据库文件的路径。

### 使用
1. 在命令行中运行以下命令启动程序：
```bash
python main.py
```
2. 输入要连接的B站直播间编号。
3. 按下`Enter`键开始监听弹幕流。

当有观众发送弹幕消息时，机器人将自动生成回复并将其转换为语音。声音文件将被保存并立即播放。

### 如何训练自己的AI？
- 打开`db.txt`，写入你想要训练的内容，格式如下
```
问
答
问
答
```
- 将文件重命名为`db.txt`
- 在命令行中运行以下命令启动程序：
```bash
python train.py
```
- 训练完的模型名叫`db.sqlite3`，直接双击`main.py`即可使用
- 没有语料？快来加群下载吧！[745682833](https://jq.qq.com/?_wv=1027&k=IO1usMMj)

### 常见问题
1. 提示缺少en-core-web-sm，打开终端输入
```bash
python -m spacy download en_core_web_sm
```
2. 报错：no module named ‘spacy’解决办法
```bash
pip install spacy
```

### TODO
- [ ] 优化ChatterBot
  - [ ] 重写ChatterBot

### 许可证
MIT许可证。详情请参阅LICENSE文件。
