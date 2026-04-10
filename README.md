# cugb ·污染物数据库演示

四氯化碳（CCl₄）动力学 / 热力学数据浏览：`index.html` + CSV。

## 本地预览

```bash
python3 -m http.server 8765
```

浏览器打开 <http://localhost:8765/index.html>。

## GitCode Pages（可选）

在仓库 **设置 → Pages** 中启用静态托管后，使用仓库提供的站点地址访问 `index.html` 即可（与 CSV 同源，无需额外跨域配置）。

## 文件说明

| 文件 | 说明 |
|------|------|
| `index.html` | 前端页面 |
| `CCl4动力学.csv` | 动力学数据 |
| `CCl4热力学.csv` | 热力学数据 |
| `CCl4.csv` | 合并/备用数据 |

**请勿**将个人访问令牌、密码等写入本仓库或提交到 Git 历史。
