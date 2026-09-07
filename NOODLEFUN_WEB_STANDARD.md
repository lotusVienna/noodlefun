# Noodle Fun Web 开发与文件结构规范

> 本文件是 Noodle Fun 网站的长期开发规范。
> 后续新增、修改或重构网站功能时，应优先遵循本规范。

---

## 1. 项目定位

Noodle Fun 官方网站：

- 域名：noodlefun.at
- GitHub：lotusVienna/noodlefun
- 当前部署方式：GitHub Pages
- 当前网站类型：静态网站
- 当前重点：品牌展示、菜单展示、Wolt / foodora 导流、Google Review、联系方式

未来网站可以逐步扩展为自己的在线点餐系统，但当前阶段不实现在线点餐。

---

## 2. 项目目录

### 2.1 正式网站代码

\`\`\`
~/projects/web/noodlefun/
\`\`\`

该目录是正式网站 Git 仓库。

对应 GitHub：

\`\`\`
git@github.com:lotusVienna/noodlefun.git
\`\`\`

### 2.2 原始菜品素材库

\`\`\`
~/projects/Noodlefun_Assets/
\`\`\`

该目录只用于保存原始图片素材。

目前主要结构：

\`\`\`
Noodlefun_Assets/
└── dish-photos/
    ├── appetizers/
    ├── bento/
    ├── desserts/
    ├── main-dishes/
    ├── menus/
    ├── poke-bowls/
    ├── ramen/
    ├── rice-noodle-boxes/
    ├── salads/
    ├── soups/
    ├── special-rolls/
    ├── sushi-maki/
    └── temaki/
\`\`\`

原则：

- 原始菜品照片不直接作为网站代码使用
- 不把整个原始素材库复制进 GitHub
- 网站只保存经过选择和优化后的 Web 图片
- 原始素材库与正式网站代码分离

---

## 3. 正式网站当前结构

\`\`\`
noodlefun/
├── CNAME
├── README.md
├── NOODLEFUN_WEB_STANDARD.md
├── index.html
├── styles.css
├── script.js
│
├── assets/
│   ├── LOGO 1024 x 475.png
│   ├── TV1.png
│   ├── TV2.png
│   ├── TV3.png
│   ├── TV4.png
│   ├── wolt-logo.png
│   └── foodora-logo.png
│
└── pages/
    ├── datenschutz.html
    └── impressum.html
\`\`\`

---

## 4. 文件职责

### index.html

网站主页。

负责：

- 页面结构
- Hero
- 菜单入口
- 平台入口
- Google Review
- 关于我们
- 联系方式
- 营业时间
- Footer

不要在 HTML 中堆积大量 CSS。

### styles.css

统一管理网站视觉样式。

包括：

- Layout
- Typography
- Colors
- Buttons
- Cards
- Navigation
- Responsive Design
- Mobile Design
- Animation

原则：

- 优先使用现有 CSS 系统
- 修改样式前先搜索已有 class
- 尽量避免重复 CSS
- 不随意增加 inline style

### script.js

负责网站交互。

目前主要包括：

- Mobile Navigation
- 菜单交互
- 前端 UI 行为

未来可以逐步增加：

- 菜品筛选
- Shopping Cart
- Checkout
- Order Status

但功能增加后应保持结构清晰。

### assets/

只放正式网站使用的图片和静态资源。

原则：

- 使用优化后的图片
- 不放原始 PSD
- 不放大型原始素材
- 不放无关文件
- 文件名尽量使用清晰、稳定的命名

### pages/

保存独立页面。

例如：

\`\`\`
pages/impressum.html
pages/datenschutz.html
\`\`\`

未来可以继续增加：

\`\`\`
pages/menu.html
pages/contact.html
\`\`\`

只有在页面内容确实需要独立 URL 时才建立新 HTML 页面。

---

## 5. 菜品图片规范

原始图片：

\`\`\`
~/projects/Noodlefun_Assets/dish-photos/
\`\`\`

正式网站图片：

\`\`\`
~/projects/web/noodlefun/assets/
\`\`\`

未来正式菜单图片建议：

\`\`\`
assets/menu/
├── appetizers/
├── bento/
├── desserts/
├── main-dishes/
├── menus/
├── poke-bowls/
├── ramen/
├── rice-noodle-boxes/
├── salads/
├── soups/
├── special-rolls/
├── sushi-maki/
└── temaki/
\`\`\`

---

## 6. 图片命名规范

正式网站文件名优先使用：

\`\`\`
lowercase-with-hyphens
\`\`\`

例如：

\`\`\`
knuspriges-huhn-mit-pommes.png
acht-schaetze.png
gebackene-gyoza.png
lachs-maki.png
\`\`\`

避免：

\`\`\`
IMG1234.png
new.png
final-final.png
test.png
图片.png
\`\`\`

也尽量避免在正式网站文件名中使用：

- 空格
- 特殊字符
- 临时版本号
- 文件大小信息

---

## 7. TV1–TV4 的规则

当前：

\`\`\`
assets/TV1.png
assets/TV2.png
assets/TV3.png
assets/TV4.png
\`\`\`

这些图片属于完整菜单展示。

在新的独立菜品菜单完成并确认之前：

**不要删除 TV1–TV4。**

它们可以继续作为：

- 完整菜单参考
- 备用菜单
- 网站现有菜单展示

未来新的 Individual Dish Menu 完成并稳定后，再决定是否保留或移除。

---

## 8. 未来 Individual Dish Menu

未来菜单采用：

\`\`\`
分类
↓
菜品卡片
↓
图片
↓
菜名
↓
描述
↓
价格
\`\`\`

桌面端：

\`\`\`
3–4 columns
\`\`\`

移动端：

\`\`\`
1–2 columns
\`\`\`

每个菜品原则上拥有独立图片。

---

## 9. 未来菜品数据结构

未来如果进入真正的菜单系统，应逐渐从 HTML 中分离菜品数据。

推荐结构：

\`\`\`
id
name
category
description
price
image
available
\`\`\`

例如：

\`\`\`
id: knuspriges-huhn-pommes
name: Knuspriges Huhn mit Pommes
category: menus
description: ...
price: 7.60
image: assets/menu/menus/knuspriges-huhn-mit-pommes.png
available: true
\`\`\`

这样未来才能比较容易加入：

- 菜品上下架
- 分类筛选
- 价格修改
- 在线购物车
- 后台管理

---

## 10. 响应式设计

网站必须同时适配：

- 手机
- 平板
- Laptop
- Desktop

优先：

\`\`\`
Mobile First
\`\`\`

重点检查：

- Header
- Navigation
- Hero
- Menu
- Buttons
- Cards
- Footer
- 图片比例
- 文字换行

修改网站后至少检查：

\`\`\`
Mobile
Desktop
\`\`\`

两个主要尺寸。

---

## 11. 外部平台

Wolt 和 foodora 是独立订单平台。

网站只负责：

\`\`\`
Noodle Fun Website
        ↓
Wolt / foodora
\`\`\`

当前阶段：

- 不复制平台订单
- 不在网站保存平台订单
- 不自行处理平台支付
- 不假设 Wolt / foodora API 已经存在

未来如果有正式 API 或官方集成，再单独设计。

---

## 12. Google Review

网站可以提供：

\`\`\`
Google Review
\`\`\`

入口。

目标：

\`\`\`
顾客完成消费
↓
访问 Google Review
↓
留下评价
\`\`\`

不要设计复杂的评论系统。

---

## 13. 在线点餐系统

在线点餐属于未来功能。

目标架构：

\`\`\`
Customer
   ↓
Noodle Fun Website
   ↓
Cart
   ↓
Checkout
   ↓
Payment
   ↓
Backend
   ↓
Restaurant Dashboard
\`\`\`

未来可以考虑：

\`\`\`
Cloudflare Workers
Cloudflare D1
Stripe
\`\`\`

但在正式开始开发前，不提前把这些系统加入当前静态网站。

---

## 14. 未来订单状态

推荐：

\`\`\`
NEW
↓
ACCEPTED
↓
PREPARING
↓
READY
↓
COMPLETED
\`\`\`

如果餐厅拒绝：

\`\`\`
NEW
↓
REJECTED
\`\`\`

订单状态必须由服务器控制，不能只依赖浏览器前端。

---

## 15. 支付安全

未来如果加入在线支付：

前端：

\`\`\`
创建付款
\`\`\`

服务器：

\`\`\`
验证付款
\`\`\`

最终订单状态：

\`\`\`
Payment confirmed
↓
Order accepted
\`\`\`

不能只根据浏览器显示的支付成功页面判断付款成功。

任何：

- API Key
- Secret
- Payment Secret
- Database Secret

都不能直接写进：

\`\`\`
index.html
styles.css
script.js
\`\`\`

也不能提交到 GitHub。

---

## 16. SEO

网站至少应保持：

- 正确 `<title>`
- Meta Description
- 正确 Heading 层级
- 图片 `alt`
- Restaurant Structured Data
- 正确地址
- 正确营业时间
- 正确电话
- 正确网站域名

地址：

\`\`\`
Alserstraße 19/5
1080 Wien
Austria
\`\`\`

---

## 17. 法律页面

网站应保持：

\`\`\`
pages/impressum.html
pages/datenschutz.html
\`\`\`

任何新增数据收集功能，例如：

- Newsletter
- Contact Form
- Online Order
- Customer Account
- Payment

都必须重新检查 Datenschutz 要求。

---

## 18. Git 规范

正式修改前：

\`\`\`
git status
\`\`\`

修改完成后：

\`\`\`
git diff
\`\`\`

确认没有问题：

\`\`\`
git status
\`\`\`

然后：

\`\`\`
git add .
git commit -m "Describe the change"
git push
\`\`\`

Commit 应描述实际修改。

例如：

\`\`\`
Update menu layout
Add dish images
Improve mobile navigation
Update restaurant information
Add new menu item
\`\`\`

---

## 19. 修改文件前的原则

修改前先确认：

1. 文件在哪里
2. 文件负责什么
3. 是否有其他页面引用
4. 是否影响 GitHub Pages
5. 是否影响移动端
6. 是否影响现有链接

尤其不要因为“看起来没用”就直接删除文件。

---

## 20. 删除文件原则

删除前：

\`\`\`
find . -name "filename"
\`\`\`

确认引用：

\`\`\`
grep -R "filename" .
\`\`\`

确认没有使用后再删除。

删除之后：

\`\`\`
git diff --stat
git status
\`\`\`

检查 Git 是否识别到了预期的删除。

---

## 21. 域名与部署

正式域名：

\`\`\`
noodlefun.at
\`\`\`

GitHub Pages：

\`\`\`
main branch
/
\`\`\`

根目录：

\`\`\`
CNAME
\`\`\`

CNAME 内容：

\`\`\`
noodlefun.at
\`\`\`

不要随意删除或修改 CNAME。

如果网站代码正常但域名出现问题：

**先检查 GitHub Pages / DNS，不要直接修改网站代码。**

---

## 22. 不应该放进 GitHub 的内容

禁止提交：

\`\`\`
.env
API Keys
Passwords
Payment Secrets
Private Keys
原始 PSD
大型原始图片库
私人文件
内部财务文件
客户个人数据
\`\`\`

---

## 23. 当前项目边界

本项目主要管理：

\`\`\`
~/projects/web/noodlefun
~/projects/web/noodlefun-promo
~/projects/Noodlefun_Assets
\`\`\`

其他项目默认不要修改。

尤其不要因为“看起来相关”而自动修改其他 Git 仓库。

---

## 24. 开发工作流程

以后修改 Noodle Fun 网站，推荐按照：

\`\`\`
1. 明确需求
      ↓
2. 检查当前文件
      ↓
3. 修改
      ↓
4. 本地检查
      ↓
5. 检查 Git diff
      ↓
6. Commit
      ↓
7. Push
      ↓
8. 检查 GitHub Pages
      ↓
9. 检查 noodlefun.at
\`\`\`

---

## 25. 未来扩展原则

网站未来可以逐步发展：

\`\`\`
Phase 1
静态品牌官网
        ↓
Phase 2
独立菜品菜单
        ↓
Phase 3
购物车 / 在线点餐
        ↓
Phase 4
餐厅订单后台
        ↓
Phase 5
支付 / 自动化 / 打印
\`\`\`

每个阶段都应该保持：

- 前一阶段继续正常工作
- 不为了未来功能过早增加复杂度
- 数据与 UI 尽量分离
- 敏感信息放服务器端
- 不重复建设已经存在的平台功能

---

## 26. 核心原则

Noodle Fun 网站长期遵循：

> 简单、稳定、可维护，再逐步扩展。

优先级：

\`\`\`
稳定
>
可维护
>
速度
>
功能数量
\`\`\`

任何新功能都应该先回答：

1. 顾客真的需要吗？
2. 餐厅真的需要吗？
3. 当前阶段需要吗？
4. 会不会增加不必要的维护成本？
5. 是否会影响现有网站？

如果不需要，现在不要做。

---

## 27. 当前状态

当前网站：

\`\`\`
Static Website
GitHub Pages
Custom Domain
Responsive Design
Wolt Link
foodora Link
Google Review
Impressum
Datenschutz
TV1–TV4 Menu
\`\`\`

当前不包含：

\`\`\`
Online Ordering
Shopping Cart
Payment
Restaurant Dashboard
Order Database
Employee App
Kitchen Printer
\`\`\`

这些属于未来阶段。
