# 学术主页模板

本模板为 GitHub 账号 `lihuiximath` 准备。主页地址为 `https://lihuiximath.github.io/`，网站仓库为 `lihuiximath/lihuiximath.github.io`。

页面结构参考 [Shaoyun Yi 的学术主页](https://yishaoyun.github.io/syi/)，重新编写 HTML 和 CSS；不包含参考站的照片、个人资料或论文。姓名与照片使用占位标签，其他内容留空。没有第三方依赖，也不需要安装或构建。

## 注册 GitHub

1. 在自己的浏览器中打开 [GitHub 注册页](https://github.com/signup)。
2. 可以用 Gmail 邮箱注册，也可以选择 **Continue with Google**。免费个人账号足够。
3. 选择一个可用的用户名。个人主页地址将是 `https://用户名.github.io/`。
4. 自己设置密码、完成可能出现的人机验证、阅读并接受条款、验证邮箱。不要在聊天中发送密码或验证码。

GitHub 的注册说明：[Creating an account on GitHub](https://docs.github.com/en/account-and-profile/how-tos/account-management/creating-an-account-on-github)。

## 上线网站

1. 登录 GitHub，点击右上角 **+ → New repository**。
2. 仓库名填写 **lihuiximath.github.io**。其他账号则填写其对应的 `用户名.github.io`。
3. 选择 **Public**，开启 **Add README**，点击 **Create repository**。
4. 在仓库首页点击 **Add file → Upload files**。把本目录中的网站文件和 `assets`、`papers` 文件夹上传到仓库根目录，再提交更改。`index.html` 应直接位于仓库根目录，不能多套一层 `academic-homepage` 文件夹。
5. 打开 **Settings → Pages**。在 **Build and deployment** 中将 **Source** 设为 **Deploy from a branch**，选择 **main** 和 **/(root)**，点击 **Save**。
6. 部署完成后，在 Pages 设置页点击 **Visit site**。GitHub 官方说明更新最多可能需要约 10 分钟。

如果拿到的是压缩包，请先解压，再上传其中的文件；GitHub 不会自动把上传的 ZIP 解压成网站。

免费账号的 GitHub Pages 需要公开仓库。上传到公开仓库的文件可被他人查看，邮箱是否写在主页上由你决定。

官方说明：[Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)、[Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。

## 编辑内容

| 文件 | 用途 |
| --- | --- |
| `index.html` | 姓名、单位、联系方式、简介、研究方向、论文和数学链接 |
| `styles.css` | 白底、字体、蓝色链接、间距和手机排版 |
| `teach.html` | 教学 |
| `seminar.html` | 研讨班 |
| `talk.html` | 学术报告 |
| `miscellany.html` | 其他信息 |
| `assets/` | 个人照片、简历 PDF 等 |
| `papers/` | 想在主页公开的论文 PDF |

用浏览器打开 `index.html` 就能本地预览。各个页面中的 HTML 注释标出了需要填写的位置。

## 上传数学论文

### 方式一：在学术主页提供 PDF

1. 在网站仓库中打开 `papers` 文件夹，点击 **Add file → Upload files**。
2. 上传论文，例如 `covering-systems-v1.pdf`，提交更改。
3. 编辑 `index.html`，在 `<ol class="publications" reversed>` 内添加一条真实论文记录：

```html
<li>
  <strong>你的论文题目</strong> (with 合作者).<br>
  <em>Preprint</em>, 2026.
  [<a href="papers/covering-systems-v1.pdf">PDF</a>]
</li>
```

以后有 arXiv 或 DOI，再按真实链接增加相应入口。示例不代表已有论文或发表记录。

### 方式二：给每篇论文建立研究仓库

若希望同时公开论文、LaTeX 源码、计算程序或 Lean 证明，可另外建一个以论文简称命名的仓库。这与 [OpenAI 的 Consistency Models 项目](https://github.com/openai/consistency_models) 用 README 介绍论文并提供相关代码的方式类似。例如：

```text
paper-short-name/
  README.md       # 题目、作者、摘要、版本、论文链接和引用方法
  paper.pdf       # 论文 PDF
  src/            # LaTeX 源码与 BibTeX（如需公开）
  code/           # 计算程序（如有）
  lean/           # Lean 形式化证明（如有）
  CITATION.cff    # 引用元数据（可选）
```

只上传 PDF 时，不必创建这些额外目录。在个人主页的论文条目中添加该 GitHub 仓库的链接即可。仓库中的 README 会作为项目介绍显示。

浏览器上传单个文件上限为 **25 MiB**，命令行上传普通 Git 文件上限为 **100 MiB**。官方操作说明：[Adding a file to a repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)。

GitHub 用于展示和版本管理；上传文件并不等于期刊发表，也不自动产生 DOI。需要研究成果 DOI 时，可以另行使用 Zenodo 等存档服务。只上传你有权公开的版本。
