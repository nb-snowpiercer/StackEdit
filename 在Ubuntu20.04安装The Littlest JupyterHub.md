
# 在Ubuntu20.04安装The Littlest JupyterHub

** The Littlest JupyterHub** 支持云端安装和本地安装，本教程介绍在**Ubuntu 20.04**本地安装**TLJH**，预备工作：首先需要一台安装**Ubuntu20.04**的服务器。

警告

**不要**直接在您的笔记本电脑或个人计算机上安装 TLJH！ 当直接运行时，它很可能会打开可利用的安全漏洞 在您的个人计算机上。

注意

不支持在 docker 容器_中_运行 TLJH，因为我们依赖于 在系统上。如果要在本地运行 TLJH 进行开发，请参阅[设置开发环境](https://tljh.jupyter.org/en/latest/contributing/dev-setup.html)。

## 目标

在本教程结束时，您应该有一个带有一些管理员的JupyterHub。 用户和要在其上运行安装包的用户环境 您有权访问的服务器。

## 先决条件

1.  对命令行有些熟悉。
    
2.  运行 Ubuntu 20.04+ 的服务器，您具有 root 访问权限（推荐使用 Ubuntu 22.04 LTS）。
    
3.  您的服务器上至少有 **1GB** 的 RAM。
    
4.  能够进入服务器并从提示符运行命令。`ssh`
    
5.  可以从目标受众的浏览器访问服务器的 **IP 地址**。
    

如果遇到问题，请查看自定义服务器安装的特定[故障排除指南](https://tljh.jupyter.org/en/latest/troubleshooting/providers/custom.html)。

## 第 1 步：安装最小的 JupyterHub

1.  使用终端程序，通过 SSH 连接到您的服务器。这应该会给你一个提示，你可以 键入命令。
    
2.  确保已安装`python3` ，`python3-dev`，`curl`和`git`。
```    
    sudo apt install python3 python3-dev git curl
```    
4.  复制下面的文本，并将其粘贴到终端中。为此替换为第一个**管理员用户**的名称 JupyterHub.选择您喜欢的任何名称（不要忘记删除括号！ 此管理员用户可以在设置 JupyterHub 后登录，并且 可以根据自己的需要进行配置。**记得添加您的用户名**！`<admin-user-name>`
    
    curl -L https://tljh.jupyter.org/bootstrap.py | sudo -E python3 - --admin <admin-user-name>
    
    注意
    
    请参阅安装程序做什么？，如果您想确切地了解[安装程序正在做什么。](https://tljh.jupyter.org/en/latest/topic/installer-actions.html)[自定义安装程序记录](https://tljh.jupyter.org/en/latest/topic/customizing-installer.html)了可传递给安装程序的其他选项。
    
5.  按下开始安装过程。这将需要5-10分钟， 并会说安装过程何时完成。`Enter``Done!`
    
6.  复制服务器的公共 **IP**，然后尝试从 您的浏览器。如果一切顺利，这应该会给你一个JupyterHub登录页面。`http://<public-ip>`
    
7.  使用您在步骤 3 中使用的**管理员用户名**登录。您可以选择任何 您想要的密码。使用 强密码并在某处记下它，因为这将是密码 从现在开始的管理员用户帐户。
    
8.  恭喜，您有一个正在运行的 JupyterHub！
    

## 第 2 步：添加更多用户

Most administration & configuration of the JupyterHub can be done from the web UI directly. Let’s add a few users who can log in!

1.  In the File menu select the entry for the **Hub Control Panel**.
    
2.  In the control panel, open the **Admin** link in the top left.
    
    This opens up the JupyterHub admin page, where you can add / delete users, start / stop peoples’ servers and see who is online.
    
3.  Click the **Add Users** button.
    
    A **Add Users** dialog box opens up.
    
4.  Type the names of users you want to add to this JupyterHub in the dialog box, one per line.
    
    You can tick the **Admin** checkbox if you want to give admin rights to all these users too.
    
5.  单击对话框中的**添加用户**按钮。您的用户现已添加 到JupyterHub！当他们第一次登录时，他们可以设置 密码 - 并在将来使用它再次登录。
    

恭喜，您现在有一个多用户 JupyterHub，您可以添加任意 用户到！

## 第 3 步：为所有用户安装 conda / pip 包

**用户环境**是所有用户共享的 conda 环境 在JupyterHub中。在此环境中安装的库会立即生效 可供所有用户使用。管理员用户可以在此环境中安装包 跟。`sudo -E`

1.  以管理员用户身份登录并在 Jupyter 笔记本中打开终端。
    
2.  从 [conda-forge](https://conda-forge.org/) 安装 [gdal](https://anaconda.org/conda-forge/gdal)。
    
    sudo -E conda install -c conda-forge gdal
    
    这是非常重要的！`sudo -E`
    
3.  [在那里](https://pypi.org/project/there)安装`pip`
    
    sudo -E pip install there
    

这些软件包现在可供JupyterHub中的所有用户使用。 如果用户已经运行了 python 笔记本，他们必须重新启动笔记本的 内核以使新库可用。`gdal``there`

有关详细信息，请参阅[安装 conda、pip 或 apt 包](https://tljh.jupyter.org/en/latest/howto/user-env/user-environment.html#howto-user-env-user-environment)。

## 第 4 步：设置 HTTPS

一旦你准备好真正运行你的服务器，并有一个域，这是一个很好的 想法直接进入[启用HTTPS](https://tljh.jupyter.org/en/latest/howto/admin/https.html)。

> Written with [StackEdit中文版](https://stackedit.cn/).

# Jupyter NoteBook / JupyterLab / JupyterHub 区别与关系简介

标签：

[Python](https://www.imooc.com/article/tag/18)[人工智能](https://www.imooc.com/article/tag/66)

收藏

-   JupyterHub 是为多个用户提供 Jupyter Notebook 的集成服务系统，JupyterHub 下用户环境彼此隔离，无法相互共享，每个用户需要单独配置自己的 Python/Conda 环境等。
    
-   JupyterHub 与 Jupyter Notebook/Lab 并非包直接含关系，JupyterHub 初始安装不包含 Jupyter Notebook/Lab，二者甚至不在一台服务器上，需要各自搭建后，通过配置组合在一起。
    
-   JupyterHub、Jupyter Notebook/Lab 分别有自己的仓库、文档、技术栈（如：除 Python、H5 外，JupyterHub 涉及 NodeJS，JupyterLab 涉及 TypeScript）。因此，JupyterHub 与 Jupyter Notebook/Lab 的接口、主题、插件等定制开发也是分别独立的项目范畴。
    
-   JupyterHub 支持第三方 Oath 认证登录，需要另外开发配置。常见的包括 GitHub、GitLab、Google 等（主要针对编程群体，因此不包括 _Facebook_、_Twitter_）。
    
-   JupyterHub 下又分为三项目：[JupyterHub](https://github.com/jupyterhub/jupyterhub)、[TLJH](https://github.com/jupyterhub/the-littlest-jupyterhub)、[Z2JH](https://github.com/jupyterhub/zero-to-jupyterhub-k8s)，每个项目都各自的文档系统、Git仓库、环境配置。每个项目的环境搭建方式大概又各可分为 3 种方式：Conda/Pip 安装、Docker 安装、Dev 环境安装。对应到开发，要根据具体需求确定一个方向，搭建配置指定的环境项目。
    
-   [JupyterHub](https://github.com/jupyterhub/jupyterhub)、[TLJH](https://github.com/jupyterhub/the-littlest-jupyterhub)、[Z2JH](https://github.com/jupyterhub/zero-to-jupyterhub-k8s) 的应用场景各有不同:
    
    -   JupyterHub：原始系统 – 环境搭建配置方式灵活、可控性强，相应出错几率相对较大
        
    -   TLJH（The Littlest JupyterHub）：发行版本 – 把 JupyterHub 搭建在一台服务器上，支持 1 ~ 50 个用户（github 描述为 1 ~ 50，文档描述为 1 ~ 100 ）
        
    -   Z2JH（Zero to JupyterHub）：发行版本 – 针对 100 以上用户量，安全稳定性要求高，计划应用 Docker 容器，需要搭建 Kubernetes 集群，对运维水平要求高
        
-   综上，将 Jupyter 系列产品关系总结如下图：
    
    ![Jupyter 系列产品关系](https://img1.sycdn.imooc.com/5e4d4b0f00010a4819340926.jpg)
    
    -   暂定搭建环境方案（根据需求调整）：
        
        -   线上环境：The Littlest JupyterHub + JupyterLab
            
        -   开发环境：JupyterHub + JupyterLab
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDM5NzQxMzIsNTM0ODE1MjAyXX0=
-->