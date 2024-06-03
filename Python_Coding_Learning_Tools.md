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

## Markovify
简介：是一个简单易用的 Python 库,用于基于马尔可夫链生成随机文本。投喂大量文本之后，它会模仿文风生成随机的语句就是了。

## Pipenv  
简介：“Python Dev Workflow for Humans”，我个人理解来说，它就是用于管理python虚拟环境和对应环境下依赖关系管理的一个工具。  
网址：https://docs.python-guide.org/dev/virtualenvs/  
1. 我的电脑上是通过**brew**来安装的pipenv（**自动部署**了，不像用pip或pip3来安装那样需要绑定在系统中某个版本的Python里【似乎如此】）。
1. 我只需记得**常用命令**：
   - 在虚拟环境激活状态下,运行 `exit` 命令或按下 Ctrl+D。
   - 在项目目录下运行 `pipenv shell` 命令。
   - `pipenv --rm` 可以删除当前项目的 Pipenv 虚拟环境。
   - `pipenv install --python 3.11` 可以**指定使用 Python3.11版本**创建虚拟环境（但前提是系统里有py3.11，否则pipenv不会自动下载安装Python）。
   - `pipenv install` 在本virtual env中**安装**项目需要的**依赖**。
        - `pipenv install ‘xxx’`命令仅用于安装依赖包（python library）而已。
   - `pipenv install -r ...PATH.../requirements.txt` 在本virtual env中**批量安装 requirements.txt 文件中列出的所有依赖包**。
       - 其中`-r`的意思就是`--requirement`的缩写，表示从文件中读取依赖项。
       - 常规的命令是`pipenv install -r requirements.txt`（此情形一般是requirement文件与Pipfile和Pipfile.lock在*同一个根目录路径*下时）
       - 这个命令相当于在传统的 pip 命令中使用的 pip install -r requirements.txt，用于**批量安装 requirements.txt 文件中列出的所有包**。
   - `pip freeze > requirements.txt`生成一个包含所有依赖的文件.  
1. **为什么要用pipenv**给项目创建虚拟环境？  
**核心**：即**用于安装*第三方库python library***到（to）*virtual env* 而不是 *系统全局*，这对于管理Python项目有几个关键的好处：
- 隔离依赖：每个Python项目可能需要不同版本的第三方库。使用虚拟环境可以避免版本冲突。如果所有项目都使用系统全局环境，一个项目更新了某个库的版本，可能会破坏依赖于该库旧版本的其他项目。
- 保持系统整洁：随着时间的推移，如果在全局环境中安装了许多库，你的系统可能会变得杂乱无章，很难跟踪哪些是当前项目需要的，哪些是过去遗留的。虚拟环境允许你仅为当前工作的项目安装所需的包。
- 易于维护：使用虚拟环境，你可以通过简单的**`pip freeze > requirements.txt`**来生成一个包含所有依赖的文件，这使得在不同机器或环境中复制项目变得非常简单。
- 清理简单：当一个项目完成或者不再需要时，你可以简单地删除对应的虚拟环境文件夹，而不用担心会影响到系统环境或其他项目。
- 性能问题：虚拟环境对电脑的性能几乎没有影响。电脑变卡通常是因为CPU或内存资源被大量消耗，而虚拟环境中的库只有在被激活并使用时才可能消耗资源。


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


## 使用Jekyll主题Themes（例如，minima）
关于GitHub Pages上可以使用的Jekyll（一个ruby的gem，for网页制作）主题themes合集：
网址：https://pages.github.com/themes/
- 常用：[`正在使用的：minima`](https://github.com/jekyll/minima)
    - **使用：必须从GitHub上克隆整个仓库到本地**，因为minima在ruby.org上只更新到2.5.1版本，但实际上在GitHubPages上用的是3.0版本了，所以无法在本地通过bundle install或者gem install安装到3.0版本及以上的依赖包。
    - **经历过的错误**：minima3.0的特色就是主页直接显示所有posts（跟使用的版本有关，跟_config.yml或者Gemfile里的设置基本无关。
    - minima看似极简，其实反而是众多themes里面架构最复杂的。
- 备用：[`商务感：cayman`](https://github.com/pages-themes/cayman)和[`私人博客感：hacker`](https://github.com/pages-themes/hacker)
