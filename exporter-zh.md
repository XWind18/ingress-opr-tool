## OPR Exporter

"OPR exporter" 是一个用于 [Tampermonkey](https://tampermonkey.net/) 的插件（不是 IITC 或 IITCm），当你加载 [OPR](https://opr.ingress.com/nominations)（显示你所有提名的页面）时会自动运行。  
首次使用时，它会提示你输入在 [OPR Planner](https://github.com/XWind18/ingress-opr-tool) 中使用的 URL 来存储候选数据，然后它会使用你的提名来更新这些数据。

### 它如何处理候选：
假设你还没有在 IITC 中添加任何内容，那么它会为 OPR 网站上显示的状态为"投票中"或"排队中"的每个候选在 IITC 中添加一个"已提交"标记。  
现在这些标记将被 Exporter 插件跟踪，所以当你将来再次加载页面时，如果它们被批准，它们将从地图中移除（你不再需要它们）。  
另一方面，如果它们被拒绝、标记为重复或者你撤回了这些候选，它们将在地图上标记为"已拒绝"，这样你就可以轻松记住要移除的位置（可能 Wayspot 已经被其他人批准了），或者将来再次提交它们。
当然，如果你之前已经计划好了，那些位置上已经有标记了，所以插件会尝试查找距离新发现的候选不到 20 米的任何此类候选，并删除现有的候选，以防止地图上出现重复标记。

## 安装
你必须在浏览器中运行 Tampermonkey 扩展（IITC mobile 不支持），并添加 [此脚本](https://github.com/XWind18/ingress-opr-tool/raw/main/opr-exporter.user.js?inline=false)。  
现在只需登录 OPR 并加载你的提名页面，第一次加载时会提示你输入在 OPR Planner 中使用的脚本 URL，粘贴它并等待几秒钟，然后在另一个标签页中加载 IITC，你就会看到待处理提名的标记。  
之后，你只需要加载页面并在显示所有候选后等待几秒钟即可。
