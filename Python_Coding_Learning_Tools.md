## W3Schools
简介：tutorial板块，有在线编译器直接可实操coding的过程（省去配置本地编译器了）；基础功能介绍适合初学。
网址：https://www.w3schools.com/python/python_lambda.asp

## Hugging Face
简介：一个（AI大）模型Models分享平台，也分享数据Dataset，同时也做tutorial教程。
    他们最著名的Transformer模型（GPT、GPT-2、BERT等语言模型早期，2018年左右，就是在Transformer模型基础上做的微调）也是自然语言处理（NLP）的基础工具之一。
网址：https://huggingface.co/docs/transformers/v4.40.1/zh/quicktour

## arXiv语料库
简介：arXiv是一个免费的、开放获取的科学论文预印本存储库。由康奈尔大学图书馆运营，论文都可以完全开放被获取，且都是作者自行提交的预印本，未经同行评议。
    主要收录数学、物理、天文学、计算机科学、生物学、统计学等领域，其中计算机科学最主要（占据30%以上的内容）。里面的数据被广泛用于自然语言处理、机器学习等领域的研究。
网址：https://arxiv.org/

## NLTK (Natural Language Toolkit)
简介：一个python的自然语言处理工具库【库，需要安装，为了安装它我还因此安装了pipenv这个库来搭建虚拟环境】
网址：https://www.nltk.org/

## Pipenv
简介：“Python Dev Workflow for Humans”，我个人理解来说，它就是用于管理python虚拟环境和对应环境下依赖关系管理的一个工具。
    我的电脑上是通过brew来安装的pipenv（自动部署了，不像用pip或pip3来安装那样需要绑定在系统中某个版本的Python里【似乎如此】）。
    我只需记得：
    在虚拟环境激活状态下,运行 exit 命令或按下 Ctrl+D。
    在项目目录下运行 pipenv shell 命令。
    pipenv --rm 可以删除当前项目的 Pipenv 虚拟环境。
    pipenv install --python 3.8 可以指定使用 Python 3.8 版本创建虚拟环境。
网址：https://docs.python-guide.org/dev/virtualenvs/

## Markovify
简介：是一个简单易用的 Python 库,用于基于马尔可夫链生成随机文本。投喂大量文本之后，它会模仿文风生成随机的语句就是了。


## pyenv
简介：核心功能就是可以让你在**多个 Python 版本**之间轻松**切换**。官网简介是“Simple Python Version Management: pyenv（Python 版本管理工具）”。  
- 用它安装的python，跟系统自带的、从python官网安装的、或者通过homebrew install安装的python会在不同的路径里，且相互独立存在。  
- 先有的rbenv，再有的pyenv这个python特调版本。  
- 常用的命令：`pyenv install 3.11.2`, `pyenv global 3.11.2`, `pyenv rehash`  
网址：  
- 主页：https://github.com/pyenv/pyenv/blob/master/README.md
- Commends命令目录：https://github.com/pyenv/pyenv/blob/master/COMMANDS.md#pyenv-rehash

## rbenv (和ruby-build)
简介：接上条，核心功能是在mac上管理**多个版本的ruby**，即“rbenv is a version manager tool”。   
- 用它安装的ruby才可以被它所管理。且跟系统自带的、ruby官网安装的、homebrew安装的ruby版本同时独立存在于电脑中。
- 经验总结：rbenv的GitHub主页很简略，实际上建议参考pyenv的GitHub主页里的安装步骤来操作会更好（尤其是`-init`初始化的过程，基本要复刻puenv主页里的步骤才有效果）。
- 原理：只要rbenv在PATH里成功植入，那本台电脑的全局上，每次调用`ruby`, `gem`, `bundler`这些命令时，会默认1)先激活rbenv，2)然后rbenv在目前所在的项目路径project directory中检索一个名为`.ruby-version`的文件，3)如果有此文件，rbenv会根据文件里指认的ruby版本调用已安装好的ruby某某版在此directory中。
- 常用命令：
  - choose the Ruby version for your project with, for example:
    ```  
      cd myproject
      #choose Ruby version 3.1.2
      rbenv local 3.1.2  
      #这段命令执行完后会在本次所在的directory中创建或更新“ruby-version”这个文件。  
    ```
  - 用rbenv安装ruby：
    ```
    #举个例子安装最新版本的ruby
    rbenv install 3.2.4
    #查询目前可安装的最新稳定ruby版本列表
    rbenv install -l
    ```  
网址：https://github.com/rbenv/rbenv

## git的本地命令官方reference（在terminal中使用的）
简介：用来替换vscode自带的‘源代码管理器’功能，直接在terminal中写命令似乎有的时候会更加直接和高效。例如
网址：https://git-scm.com/docs/git#_git_commands
还有，有空上个小网课学习一下也行：[`Udacity Git课程：一个免费的互动式在线课程，帮助你快速掌握Git的基本操作。`](https://www.udacity.com/course/version-control-with-git--ud123)