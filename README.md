# 巡黔记产品线电商点击感知模拟器 V2

这是一个纯 HTML + CSS + JavaScript 页面，可以直接放到 GitHub Pages 上分享链接。

## 现在已经支持

- 本地统计：每个浏览器自己的 localStorage 统计
- 云端统计：访问者的点击会写入 Supabase 的 click_events 表
- A/B 版本切换记录
- 场景选择记录
- 商品点击/弹窗查看记录
- 反馈按钮记录：我会点击、我觉得太贵、我还没看懂差异

## 文件说明

- index.html：页面主体
- style.css：页面样式
- script.js：产品数据、交互逻辑、Supabase 数据写入
- assets/：图片素材

## 你怎么查看后台数据

1. 打开 Supabase
2. 进入你的项目
3. 左侧点 Table Editor
4. 点 click_events 表
5. 每一行就是一次用户行为记录

常看的字段：

- created_at：什么时候发生
- session_id：同一个访问者的临时编号
- ab_version：当时是 A 版还是 B 版
- scenario_id：用户选择的场景
- sku_id：用户点击的商品
- action：发生了什么动作
- price：商品价格
- feedback：反馈内容
- page_url：页面地址

## 如果后台没有数据

先检查 Supabase 里的 click_events 表是否允许公开写入：

- Policy 要允许 anon 执行 INSERT
- WITH CHECK 建议填 true

如果规则没开，页面能正常打开，但数据写不进去。

## 部署到 GitHub Pages

把这些文件上传到 GitHub 仓库根目录：

- index.html
- style.css
- script.js
- README.md
- assets 文件夹

然后在 GitHub 仓库 Settings 里打开 Pages，选择 main 分支部署即可。
