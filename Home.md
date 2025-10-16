> [!example] [[-数学-|总目录]]

> [!example]- 数学分析
>```dataview
>list 
>from #数学
>where regexmatch("-.*-" ,file.name)
>and contains(file.path, "微积分")
>sort chapter
>```

> [!example]- 线性代数
>```dataview
>list 
>from #数学
>where regexmatch("-.*-" ,file.name)
>and contains(file.path, "线性代数")
>sort chapter
>```

> [!example]- 概率论
>```dataview
>list
>from #数学
>where regexmatch("-.*-" ,file.name)
>and contains(file.path, "概率论")
>sort chapter
>```

> [!note]+ 最近编辑
>```dataview
>table WITHOUT ID file.link AS "标题", file.mtime
>from #数学 and !"模板" and !"kanban"
>where regextest("(微积分|概率论|线性代数|Other)", file.path)
>sort file.mtime desc
>limit 16
>```