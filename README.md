# QtCourse

Qt 课程实验代码。

## 实验1

在教材示例代码 samp2_4App 上加了一个"关于"工具按钮，点一下弹出窗口显示自己的
姓名、学号、班级。

```
实验1/
├── samp2_4App/                  # Qt 工程（samp2_4.pro）
│   ├── qwmainwind.ui            # 界面：加了 actAbout 这个 Action
│   ├── qwmainwind.h / .cpp      # 加了 on_actAbout_triggered() 槽函数
│   ├── res.qrc                  # 注册了 images/about.bmp
│   └── images/                  # 工具栏图标
├── 实验1报告.md
├── 截图_任务1_关于窗口.png
└── 截图_任务2_GitHub仓库.png
```

用 Qt Creator 打开 samp2_4App/samp2_4.pro，选好构建套件（我用的 Desktop Qt 6.6.0
MinGW 64-bit）直接运行就行。
