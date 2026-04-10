# cugb ·污染物数据库演示

四氯化碳（CCl₄）动力学 / 热力学数据浏览：`index.html` + CSV。

## 本地预览

```bash
python3 -m http.server 8765
```

浏览器打开 <http://localhost:8765/index.html>。

## 上传到 GitCode 仓库

在本地项目目录执行（需已配置 SSH 或 HTTPS 凭据）：

```bash
cd "/Users/xiaoyang/代码/水环/污染物数据库"   # 按你的实际路径修改
git remote -v   # 应指向 https://gitcode.com/LittleSheep223/cugb.git
git add -A
git status
git commit -m "更新演示站点"   # 有变更时再提交
git push -u origin main
```

HTTPS 推送时：**用户名**为 GitCode 账号，**密码**处填写**个人访问令牌**（勿写入仓库）。

## 开启 GitCode Pages

按平台界面二选一（以仓库 **设置** 里实际菜单为准）：

1. **内置 Pages**  
   打开仓库 → **设置** → **Pages**（或「静态网站托管」类入口）→ 选择 **`main`** 分支、根目录或 **`/public`**（若要求指定目录）→ 保存后等待部署，使用页面给出的 **https://…** 地址访问。

2. **CI/CD 发布（本仓库已含 `.gitlab-ci.yml`）**  
   GitCode 与 GitLab 类似时，流水线会把 `index.html` 与 `CCl4*.csv` 复制到 **`public/`** 并发布为 Pages。  
   请确认项目 **设置 →通用 → 可见性** 允许 **Pages**；在 **CI/CD → 流水线** 中查看 `pages` 任务是否成功。成功后访问地址一般在 **设置 → Pages** 或流水线说明中列出（常见形式为项目子路径，例如 `https://<域名>/<用户名>/cugb/`）。

若设置中暂时 **没有 Pages**：[GitCode 帮助文档](https://docs.gitcode.com/) 中部分能力仍在迭代，可先依赖 **CI成功后的 Pages 链接**，或改用 [GitHub Pages](https://pages.github.com/) 等托管同一套静态文件。

站点打开后访问 **`/index.html`** 或与平台给出的默认入口一致即可；CSV 与页面同源，无需额外跨域配置。

## 文件说明

| 文件 | 说明 |
|------|------|
| `index.html` | 前端页面 |
| `CCl4动力学.csv` | 动力学数据 |
| `CCl4热力学.csv` | 热力学数据 |
| `CCl4.csv` | 合并/备用数据 |
| `.gitlab-ci.yml` | Pages 发布用 CI（可选） |

**请勿**将个人访问令牌、密码等写入本仓库或提交到 Git 历史。
