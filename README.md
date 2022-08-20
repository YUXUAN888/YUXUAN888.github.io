# 欢迎来到 FSM Developer

> 介绍

#### 无限可能
FSM Developer 是全新的开发平台，它面向开发者，同时 FSM Developer 进行了扩展，让普通用户也加入其中。
#### 优雅开发
FSM Developer 提供所有面向开发者的工具，都非常的优雅，甚至不需要代码，或只需要部分函数。
#### 年轻项目
FSM Developer 总项目创建不到一年时间，是非常年轻，也非常有潜力。
#### 简单发布
FSM Developer 将开发成果发布，只需要创建代码仓库并提交申请，在 1 周内就能发布。
#### 开源安全
FSM Developer 所有的开发者工具或云端都是开源开放的，并且开发成果也强制将代码仓库开源，公开安全策略。

# 吐槽报

> 介绍

#### 运行原理和介绍
将所有提交至问卷网的吐槽报条目进行整理，筛选后在 FSM Server 上进行 Json 的序列化，并将 Json 文件保存以供读取。

吐槽报 API 网页为 PHP7.4 ，运行环境为 Apache 2.4.53 。

> 接入吐槽报

#### 将您的程序接入吐槽报
这非常简单，只需要反序列化吐槽报 API 内的 Json 文件即可。

将反序列化的吐槽报添加至列表，仅需获取吐槽报的条目数量，然后进行循环增加。

吐槽报 API ：

<pre>
http://101.43.69.145:666/FSM.json
</pre>

#### 部分语言代码示例

C# 语言

<pre>
Root root = JsonConvert.DeserializeObject<Root>(Get("http://101.43.69.145:666/FSM.json"));
</pre>

Go 语言

<pre>
url := "http://101.43.69.145:666/FSM.json"
		resp, err := http.Get(url)
		if err != nil {
			panic(err.Error())
		}
		bytes, err := ioutil.ReadAll(resp.Body)
		if err != nil {
			fmt.Println("读取数据错误:", err)
			return
		}
		defer resp.Body.Close()
		//fmt.Println(string(bytes))
		var kkk Root
		err = json.Unmarshal([]byte(bytes), &kkk)
		if err != nil {
			fmt.Println("反序列化失败:", err)
		}
</pre>
