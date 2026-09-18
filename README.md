# QtCourse

Qt 程序设计课程实验代码仓库。

## 目录结构

```
QtCourse/
└── 实验1/
    ├── samp2_4App/                 # 实验1 任务1：在示例代码中增加"关于"工具按钮
    │   ├── samp2_4.pro             # qmake 工程文件
    │   ├── main.cpp                # 程序入口
    │   ├── qwmainwind.h / .cpp     # 主窗口类（含"关于"槽函数）
    │   ├── qwmainwind.ui           # Qt Designer 界面文件（新增 actAbout 工具按钮）
    │   ├── res.qrc                 # 资源文件（新增 images/about.bmp）
    │   ├── AppIcon.ico             # 应用程序图标
    │   └── images/                 # 工具栏图标
    └── 截图_任务1_关于窗口.png      # 实验1 任务1 运行截图
```

## 实验1 任务1：增加"关于"工具按钮

在示例代码 `samp2_4App` 的基础上，增加了一个"关于"工具按钮，点击后弹出 About 窗口，
显示开发人员姓名、学号、班级和 Qt 版本信息。

主要改动：

| 文件 | 改动内容 |
| --- | --- |
| `images/about.bmp` | 新增"关于"按钮的 16×16 图标 |
| `res.qrc` | 注册新图标 `images/about.bmp` |
| `qwmainwind.ui` | 新增 Action `actAbout`（图标 + 文本"关于"），并加入工具栏 `mainToolBar` |
| `qwmainwind.h` | 声明槽函数 `void on_actAbout_triggered();` |
| `qwmainwind.cpp` | 在菜单栏创建"帮助"菜单并加入该 Action；实现 `on_actAbout_triggered()`，用 `QMessageBox::about()` 显示姓名、学号等信息 |

修改作者信息只需改 `qwmainwind.cpp` 顶部三行宏定义：

```cpp
#define APP_AUTHOR_NAME     QStringLiteral("梁展榕")        // 姓名
#define APP_AUTHOR_ID       QStringLiteral("2023423330214")   // 学号
#define APP_AUTHOR_CLASS    QStringLiteral("24软卓1班") // 班级（可选）
```

## 构建与运行

用 Qt Creator 打开 `samp2_4App/samp2_4.pro`，选择合适的构建套件（如 Desktop Qt 6.x MinGW 64-bit）
后直接构建运行即可。也可以命令行构建：

```bash
cd samp2_4App
qmake samp2_4.pro
mingw32-make          # 或 make / nmake，取决于所用编译器
```

运行效果：点击工具栏上的"关于"按钮（或"帮助"菜单 →"关于"），弹出如下窗口：

![关于窗口](../实验1/截图_任务1_关于窗口.png)
