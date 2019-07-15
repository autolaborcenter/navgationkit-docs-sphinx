# Autolabor 导航套件官方使用手册

本工程是 Autolabor 导航套件官方使用手册的 **`Sphinx` 工程**。

## 克隆项目

```shell
git clone https://github.com/autolaborcenter/autolabor_box_docs.git
```

### 文件说明

* `source` 目录下保存了手册的 markdown 版本。

## 编译

本工程需要 python3/pip3 环境来编译。

1. 安装 [python](https://www.python.org/) 环境（version ≥ 3.5）

   在最新版 [3.7.3](https://www.python.org/downloads/release/python-373/) 发布页选择你的平台。

2. 安装 [`Sphinx`](https://www.sphinx-doc.org) 环境及扩展

   进入项目文件夹，执行：

   ```shell
   make install_environment
   ```

3. 编译

   进入项目文件夹，执行：

   ```shell
   make clean html
   ```

   编译好的静态网站在 `build/html` 目录下。

## 贡献指南

**推送或创建合并申请前，仔细阅读下列要求。请尽量先在本地编译，预览效果。**

### 关于链接

* 链接外部网页以 `http://` 或 `https://` 开始
* 链接其他文档页直接使用相对路径索引，且**末尾不要加文件后缀名**
* 链接页内标题可使用 markdown 语法（`#目标标题`）
* `Sphinx` 不支持以 markdown 语法链接其他文档页的标题，需要应直接书写 html 锚点

### makedown 格式要求

* 使用格式

  * *斜体*用于标识新的概念或语境内含义与通常不同的**词**
  * **粗体**标识重点和需要特别提醒用户注意的**词语或句子**
  * `行内引用` 标识嵌入行内的代码
  * > 引用标识离开文章的出口或大段的注意事项。引用引起的是段落，因此结尾要有标点。
  * 代码引用注明语言
    ```markdown
    \```markdown
     这是一段代码引用
    \``` 
    ```

* 非中文与中文之间空格

  * 英文与中文之间
    ```markdown
    当 english 嵌入到中文
    ```
  * 数字与中文之间
    ```markdown
    数字两边各空 1 格
    ```
  * 内嵌引用与中文之间
    ```markdown
    一个类名 `ClassName`
    ```
  * 全角标点会吸收一个空格
    ```markdown
    这个句子后有中文句号。It's not necessary to add a white space before this sentence. 但半角标点与中文之间仍需空格。
    ```
