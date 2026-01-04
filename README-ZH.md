# ⚠️ 警告！ ⚠️

[English](README.md) | 简体中文

IITC 无法显示不在 Ingress 中的 Wayspot。你可以使用 Geospatial Browser 来查看这些 Wayspot。
1. [注册 Lightship 账户](https://lightship.dev/signin/create-account)
2. [使用 Geospatial Browser](https://lightship.dev/account/geospatial-browser/)

这样你就能看到那些不在 Ingress 中显示的额外 Wayspot。

## 项目说明

本项目基于 [Wayfarer Planner](https://gitlab.com/NvlblNm/wayfarer) 修改而来，主要变更包括：

- 🔄 将域名从 `wayfarer.nianticlabs.com` 更新为 `opr.ingress.com`
- 🎨 将所有 Wayfarer 命名统一替换为 OPR
- 📦 迁移至 GitHub 仓库便于维护和协作
- ✨ 后续将根据需要添加新功能和改进

感谢原作者的优秀工作！如果你需要原版功能，请访问 [原始项目](https://gitlab.com/NvlblNm/wayfarer)。

## OPR Planner - 帮助你规划和跟踪提名的 IITC 插件

你可以规划在哪里提交候选 Portal，确保它们距离现有 Portal 至少 20 米，如果可能的话不要与其他现有 Portal 共享同一个 17 级 Cell，甚至可以跟踪编辑请求以将事物放置在正确的位置。效果如下：

<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/markersonthemap.png"></img><br/>

你也可以使用绘图工具来完成，但这不如直接在地图上点击方便，而且可以填写额外的信息以便日后记住这是关于什么的：

<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/mapwitheditdialogue.png"></img><br/>

这也允许你在不同设备之间轻松共享数据，甚至可以与其他队友共享计划，避免重复提交同一候选，因为数据存储在 Google 表格中。

<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/filledsheet.png"></img><br/>

使用起来很简单，但如果你想创建自己的 Google 表格，需要进行一些配置。不过，完成设置后，只需安装用户脚本即可开始使用。

## A. 安装 IITC 插件

如果你想使用现有的表格，安装 <a href="https://github.com/XWind18/ingress-opr-tool/raw/main/opr-planner.user.js?inline=false">用户脚本</a>，加载 IITC 并输入脚本 URL。<br/>

<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/dialog.png"></img><br/>

你可以使用这个测试脚本 URL：
```
https://script.google.com/macros/s/AKfycbyBx4dR0s8v1ZEsnuKFARfmibHiqTY20qO0EU3vRML4y4XW6wmu/exec
```

请注意这是一个共享表格，在确认插件正常工作后，你必须使用自己的表格而不是这个。<br/>

如果你使用了任何阻止 Google 域名的扩展（如 Privacy Badger），你需要为此域名解除阻止。

功能列表在本页末尾。

## B. 如果你想创建自己的表格，请按照以下说明操作：

 1. 访问：https://docs.google.com/spreadsheets/u/0/
 2. 创建一个新的空白电子表格<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/startnewspreadsheet.png"></img><br/>

 3. 转到"扩展程序"→"Apps Script"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/extensionsmenu.png"></img><br/>

 4. 删除 Code.gs 中的内容，粘贴此 <a href="Code.gs">Code.gs</a> 文件的内容，然后点击"保存"按钮<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/setsheetscriptcontent.png"></img><br/>

 5. 转到"initialSetup"并选择函数"initialSetup"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/setinitialsetup.png"></img><br/>

 6. 点击"运行"按钮执行<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/runinitialsetup.png"></img><br/>

 7. 弹出对话框，选择"查看权限"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/authorizationrequired.png"></img><br/>

 8. 选择适当的 Google 账户<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/choosegoogleaccount.png"></img><br/>

 9. 选择"高级"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/chooseadvanced.png"></img><br/>

 10. 转到"无标题项目"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/gotountitled.png"></img><br/>

 11. 选择你的 Google 账户并点击"允许"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/chooseallow.png"></img><br/>

 12. 初始设置将运行，表格将使用正确的列和列设置进行准备（切换到工作表查看表格）<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/scriptlog.png"></img><br/><br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/sheetcolumnsfilled.png"></img><br/>

 13. 返回 Apps Script 并选择"部署"→"新建部署"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/deploy.png"></img><br/>

 14. 将"有权访问的用户"设置为"所有人"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/deploywebapp.png"></img><br/>

 15. 选择"部署"<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/copywebappurl.png"></img><br/>

 16. 点击复制来复制"网络应用"URL。稍后你将需要用到它。<br/>

 17. 安装 <a href="https://github.com/XWind18/ingress-opr-tool/raw/main/opr-planner.user.js">用户脚本</a>。首次启动时，系统会提示你输入此 URL。<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/enterscripturl.png"></img><br/>

如果你使用了任何阻止 Google 域名的扩展（如 Privacy Badger），你需要为此域名解除阻止。<br/>

你需要与所有将共享相同数据的人员和/或设备共享此 URL。
为此，你需要点击右上角的"共享"按钮来更新可以编辑电子表格的权限。
在常规访问权限下，将权限更改为"拥有链接的任何人"，并将其设置为"编辑者"。
你还应该重新访问 Apps Script 并点击"部署"。现在，转到"管理部署"。
向下滚动到"网络应用"，如果尚未选择此选项，请将"有权访问的用户"设置为任何人。

## 如何更新 code.gs 脚本

如果出于某种原因需要更新 code.gs 中的脚本，请按照以下步骤操作：
1. 用 code.gs 的新代码替换现有代码
2. 从上面的步骤 13 开始："部署"→"新建部署"
3. 在步骤 14 的对话框中，将其标记为**新**项目版本
4. 点击部署，当你看到步骤 15 的对话框时，就完成了

## 功能列表

侧边栏中添加了一个新链接"OPR"，你可以点击它打开设置对话框。<br />
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/dialog.png"></img><br/>

当你启用"在地图上点击以添加标记"复选框时，你可以在地图上点击以添加新标记<br />
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/clickonmap.png"></img><br/>

你会看到所有输入和更改都将存储在你的 Google 表格中。你可以与任何你想要的人共享表格，或保留给自己。删除标记只需从表格中删除一行即可。<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/filledsheet.png"></img>/<br/>

你可以通过点击右上角的符号在 IITC 的图层菜单中打开或关闭多个图层。<br/>
<img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/layer.png"><img src="https://github.com/XWind18/ingress-opr-tool/raw/main/assets/layerselection.png"></img><br/>

要刷新标记集，你可以使用对话框中的"更新候选数据"链接。

你可以跟踪新位置的候选以及调整现有 Portal 位置的编辑请求。

## 与 OPR 集成

你可以使用 TamperMonkey 的附加插件，使用 OPR 中跟踪的提名自动管理你的数据：
了解如何使用：[OPR Exporter](https://github.com/XWind18/ingress-opr-tool/blob/master/exporter.md)

## 与原始 TotalRecon 的差异

此插件最初是 https://github.com/Wintervorst/iitc/raw/main/plugins/totalrecon/ 的分支

我建议为原始版本提供补丁以修复一些问题和改进，但该提议被拒绝，并被告知创建自己的分支，所以就有了这个项目。

1. 删除了以前插件中一些未使用的代码，并修复了诸如启用/禁用图层时发生的错误
2. 不使用高亮器，而是提供一个带有启用添加新标记选项的对话框
3. 对话框允许在需要时更新 URL 和刷新
4. 添加了跟踪编辑请求的选项
5. 允许从地图中删除候选
6. 改进了编辑对话框的布局
7. 重命名为"OPR planner"后的所有内容 https://github.com/XWind18/ingress-opr-tool/commits/master

## 我想帮忙！

太棒了，查看 [CONTRIBUTING](CONTRIBUTING.md) 开始吧！
