# GPT-4 中文教程

## GPT-4 更新总结

1. GPT-4>GPT-4 turbo:Everything in ChatGPT

   开发应用程序将成为历史,未来只需要一个软件就是ChatGPT
   全民定制 AI助手的时代即将来临

   1. token

      1. Context length from 16k to128k
      2. 2x speed
      3. price 

         1. input token 1/3 less
         2. output token 1/2 less

   2. more control

      1. json mode

         支持json格式,让答案更好控制

      2. function calling improving

         可以同时调用多个函数

   3. 知识库

      1. from 2021 刀 2023
      2. 可以上传知识库

   4. 支持RAG(检索增强生成)

      Retrieval-Augmented Generation

      检索增强生成

      我们提供一个外部知识库,然后LLMs可以调用这些知识库来进行回答

      ```md
      from langchain.document_loaders import WebBaseLoader
      from langchain.indexes import VectorstoreIndexCreator
      loader = WebBaseLoader("http://www.paulgraham.com/greatwork.html")
      index = VectorstoreIndexCreator().from_loaders([loader])
      index.query("What should I work on?")
      ```

   5. 支持微调

   6. Integration

      GPT4 turbo集成了

      1. DALLE 3生图能力
      2. turbo with vision视觉能力
      3. TTS语音功能
      4. whisper v3听觉能力

2. **Custom GPT(GPTs)**

   Best Special for company

   我们找一个项目,然后把项目的readme.md文件转为txt文件,然后传进去
   如果是教学项目,那么就可以让它教我们项目

   如果是部署的项目,那么就可以让它教我们部署项目

   1. can be api call
   2. can upload file
   3. 在[ChatGPT](https://chat.openai.com/)可以直接发布给其他用户使用

   结合All tools,很明显一个同声传译就实现了,不需要任何编程,嵌入到一个硬件里面即可

3. GPT store

   开源,开发者的一种社区,资源下放

   1. don't more than 12 will show
   2. Revenue sharing

4. Assistant API

   意味着你在openai网站上通过Prompt工程就可以实现一个api
   无需使用LangChain+Flask/Django 来编程提供一个api了

5. All tools

   无缝融合 DALLE3,联网搜索,数据分析,上传文件

   无需手动切换模型



## 开源项目

- [gpt4-pdf-chatbot-langchain](https://github.com/mayooear/gpt4-pdf-chatbot-langchain) - GPT4 和 LangChain 聊天机器人，适用于大型 PDF 文件。
- [GPT-4 Chat UI](https://replit.com/@zahid/GPT-4-Chat-UI) - Replit GPT-4 Next.js 前端模板。
- [GPT-Prompter](https://github.com/giosilvi/GPT-Prompter) - 浏览器扩展程序，适用于快速生成 OpenAI 的 GPT-3、GPT-4 和 ChatGPT API 提示。
- [promptlib](https://github.com/jmpaz/promptlib/) - 一个可用于带有 Gradio 前端界面开发的 ChatGPT 的提示集。"

## Prompts

### 充当英语翻译者和改进者

```md
我希望你担任英语翻译员、拼写纠正员和改进员。我会用任何语言与您交谈，您将检测该语言，将其翻译并用我的文本的更正和改进版本（英文）进行回答。我希望你把我简化的A0级单词和句子替换为更漂亮、优雅、更高水平的英语单词和句子。保持含义相同，但使它们更具文学性。我希望你只回复更正、改进，不要写任何其他内容，不要写解释。我的第一句话是“istanbulu cok seviyom burada olmak cok guzel”
```

### 充当英语发音助手

```md
我希望你担任土耳其语人士的英语发音助手。我给你写句子，你只回答它们的发音，其他什么都不做。回复不能是我句子的翻译，而只能是发音。发音应使用土耳其拉丁字母进行发音。不要在回复中写解释。我的第一句话是“伊斯坦布尔的天气怎么样？”
```



### 充当Excel助手

```md
我希望你充当基于文本的 Excel。您只需回复我基于文本的 10 行 Excel 工作表，其中行号和单元格字母作为列（A 到 L）。第一列标题应为空以引用行号。我会告诉你要在单元格中写入什么内容，你只会以文本形式回复 Excel 表格的结果，而不会回复任何其他内容。不要写解释。我会写给你公式，你会执行公式，你只会以文本形式回复 Excel 表格的结果。首先，回复我一张空表。
```



### 担任人工智能写作导师

```md
我想让你担任人工智能写作导师。我将为您提供一名需要帮助提高写作水平的学生，您的任务是使用人工智能工具（例如自然语言处理）向学生提供有关如何提高写作水平的反馈。您还应该利用您的修辞知识和有关有效写作技巧的经验，以便建议学生如何更好地以书面形式表达他们的想法和想法。我的第一个要求是“我需要有人帮助我编辑我的硕士论文”。
```

### 充当旅行向导

```md
我想让你担任旅行向导。我会将我的位置写给您，您会建议我的位置附近的游览地点。在某些情况下，我还会向您提供我将参观的地点类型。您还会向我推荐靠近我的第一个位置的类似类型的地方。我的第一个建议请求是“我在伊斯坦布尔/贝伊奥卢，我只想参观博物馆。”
```



## Demo

- [GPTBot](https://github.com/LIFTE-H2/GPTBot)-一个完全无服务器的Slack机器人，具有GPT-4支持和完整的对话模式。
- [Pair](https://github.com/jiggy-ai/pair)-用于程序员与GPT-4配对编程的迭代式状态聊天界面。
- [gpt-cli](https://github.com/CristiVlad25/gpt-cli)-直接从你的终端访问GPT3、ChatGPT和GPT4。
- [狼人](https://github.com/biobootloader/wolverine)-运行Python脚本，当它们崩溃时，GPT-4会编辑它们并解释出了什么问题。
- [datasetGPT](https://github.com/radi-cho/datasetGPT)-生成文本数据集和对话数据集的命令行界面。
- [ChatGPTify](https://github.com/idilsulo/ChatGPTify)-通过ChatGPT（和GPT-4）生成Spotify播放列表。
- [Smart Connections](https://github.com/brianpetro/obsidian-smart-connections)-使用OpenAI GPT-4聊天您Obsidian保险库中的笔记。
- [Smarty GPT](https://github.com/citiususc/Smarty-GPT)-支持多个模型（包括GPT4）的提示和上下文包装器。
- [gpt-voice-conversation-chatbot](https://github.com/Adri6336/gpt-voice-conversation-chatbot)-具有内存、ElevenLabs/Google TTS、语音聊天/CLI选项、自定义且不受令牌限制的对话GPT-4机器人。


### 社区演示

- [用GPT-4写的第一本书](https://www.impromptubook.com/wp-content/uploads/2023/03/impromptu-rh.pdf)（公告[主题](https://twitter.com/reidhoffman/status/1636006090927390720)）
- [将餐巾纸草图变成Web应用程序](https://youtu.be/outcGtbnMuQ?t=972)（由OpenAI提供）
- [GPT-4试图通过请求自己的文档来逃跑](https://twitter.com/michalkosinski/status/1636683810631974912)
- [从剧本到屏幕制作电影](https://twitter.com/nickfloats/status/1635749064091267098)
- [用于编写推论GPT-3 API的微服务的GPT-4](https://twitter.com/joeprkns/status/1635969883375640577)。- 利用 GPT-4 制作 Google Chrome 扩展程序: https://twitter.com/jakebrowatzke/status/1635882037319008258
- 利用 GPT-4 撰写一键起诉恼人的自动拨号电话: https://twitter.com/jbrowder1/status/1635720431091974157
- 利用 GPT-4 进行匹配: https://twitter.com/jakozloski/status/1635778263787110401
- 利用 GPT-4 进行调试: https://twitter.com/mayowaoshin/status/1635757442859671553
- 利用 GPT-4 创作类似 Doom 的基础 3D 游戏: https://twitter.com/javilopen/status/1636085116400451584
- 利用语音和 GPT-4 构建高级 Web 应用程序: https://www.youtube.com/watch?v=lZj63vjueeU
- 利用 GPT-4 创作 Three.js 音乐可视化器: https://twitter.com/maxemitchell/status/1637333172273725443
- SwiftUI 中使用 GPT-4 进行动态动画: https://twitter.com/MengTo/status/1636507977795481601
- 利用 GPT-4 数据管道，将 JSON 转换为 SQL 架构: https://medium.com/@nschairer/gpt-4-data-pipelines-transform-json-to-sql-schema-instantly-dfd62f6d1024

### 产品集成

- Khan Academy 将 GPT-4 作为每个学生的定制导师: https://openai.com/customer-stories/khan-academy
  - GPT-4 Khan Academy 深入演示: https://www.youtube.com/watch?v=rnIgnS8Susg
- Be My Eyes 利用 GPT-4 转化视觉障碍: https://openai.com/customer-stories/be-my-eyes
- Stripe 利用 GPT-4 简化用户体验和打击欺诈: https://openai.com/customer-stories/stripe
- Duolingo 利用 GPT-4 加深对话: https://openai.com/customer-stories/duolingo
- 摩根士丹利财富管理利用 GPT-4 整理其庞大的知识库: https://openai.com/customer-stories/morgan-stanley
- 冰岛如何利用 GPT-4 保护其语言: https://openai.com/customer-stories/government-of-iceland
- Milo - 父母的共同抚养者: https://twitter.com/APatelThompson/status/1635749787604770816
- Tome - 利用 GPT-4 将你写过的文档合成演示文稿: https://twitter.com/hliriani/status/1635770323454038018- [Elicit](https://elicit.org/gpt4-waitlist) - 使用 GPT-4 在 2 亿篇研究论文中找到洞见。
- [Fin](https://twitter.com/destraynor/status/1635705919441969153) 由 [Intercom](https://www.intercom.com/) 开发的 ChatGPT 客户服务聊天机器人。
- [Magician](https://twitter.com/jsngr/status/1635696478013337600) 由 [diagram](https://diagram.com/) 开发的 AI 设计工具，可使用 GPT-4。
- GitHub [Copilot X](https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/) - AI 助推的开发者体验。
- [Cratecode](https://cratecode.com) - AI 编程助手/导师和自动文章生成器。
