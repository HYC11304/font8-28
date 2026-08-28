# my-fonts —— 字体仓库模板

这是给「FontHub 字体库网站」后台对接用的 GitHub 仓库模板。
把你的字体文件放进 `fonts/` 目录，把整个仓库上传到 GitHub 即可完成对接。

## 目录结构

```
my-fonts/
├── README.md               ← 本说明文件（会显示在 GitHub 仓库首页）
└── fonts/                  ← 后台 Path 字段填 fonts
    ├── my-font-1/          ← 每个字体一个子文件夹，名字可自定义
    │   └── （把你的 .ttf / .otf 字体文件放在这里）
    └── my-font-2/
        └── （把你的 .ttf / .otf 字体文件放在这里）
```

- 支持格式：**.ttf / .otf / .woff / .woff2**
- 目录层级不限（可以继续套子目录），`README.md` 等非字体文件会被自动忽略
- 文件夹名建议用英文小写，避免大小写和编码问题

## 使用步骤

1. 把字体文件放进 `fonts/` 下的子文件夹（网页上传单文件上限 25MB，字体文件一般没问题）
2. 到 [github.com](https://github.com) 新建仓库，**必须选 Public（公开）**
3. 在仓库页面点 **Add file → Upload files**，把本目录里的文件全部拖进去，点 Commit changes
4. 到 FontHub 后台「仓库管理」添加仓库，按下表填写：

| 后台表单字段 | 填写内容 | 示例 |
|---|---|---|
| 仓库名称（展示用） | 随意，显示给访客看 | 我的字体库 |
| Owner | 你的 GitHub 用户名 | zhangsan |
| Repo | 你在 GitHub 建的仓库名 | my-fonts |
| Branch | 分支名，默认即可 | main |
| Path | 字体所在子目录，留空 = 根目录 | fonts |

5. 点「测试连接」→ 通过后「保存仓库」，首页即可看到这些字体

## 注意事项

- 仓库必须 **Public**；如果建了 Private 仓库，需要在后台「全局设置」或仓库表单里填 GitHub Token，否则无法访问
- 修改了仓库里的字体后，后台「缓存管理」清一次列表缓存即可立即生效
- 建议在 GitHub 生成一个 Personal access token 填到后台「全局设置 → GitHub Token」：
  匿名访问 GitHub 限流 60 次/小时，配 Token 后提升到 5000 次/小时，预览更稳定
