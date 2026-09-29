# Bonavia Health — 官网静态文件

四个语言版本,均为独立的纯静态HTML文件,无需任何构建工具,可直接部署。

- `index.html` — 英文版(默认首页)
- `ru.html` — 俄文版
- `fr.html` — 法文版
- `zh.html` — 中文版(含FAQ板块 + SEO结构化数据)

## 部署到 GitHub Pages,步骤如下

1. 在 GitHub 新建一个仓库(建议命名为 `bonaviahealth` 或类似),设为 Public
2. 把这四个 `.html` 文件(以及这份 README,可选)上传到仓库根目录
3. 进入仓库 **Settings → Pages**
4. **Source** 选择 `Deploy from a branch`,**Branch** 选择 `main` / `master`,目录选 `/ (root)`,保存
5. 几分钟后,GitHub会给一个类似 `https://你的用户名.github.io/仓库名/` 的临时网址,先用这个测试网站是否正常打开(四个语言版本都点一下试试,尤其检查右上角语言切换按钮)

## 绑定 Namecheap 买的自定义域名

1. 这次打包里已经附上了 `CNAME` 文件(内容就是 `bonaviahealth.org`),不用自己再新建,和另外四个 `.html` 文件一起拖到仓库根目录上传即可
2. 回到 **Settings → Pages**,在 **Custom domain** 一栏填入同一个域名,保存
3. 去 Namecheap 后台,进入该域名的 **Advanced DNS** 设置,添加以下记录(GitHub Pages官方要求的固定IP):

   | 类型 | 主机 | 值 |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | 你的用户名.github.io |

4. DNS生效一般需要几分钟到几小时,生效后 GitHub Pages 设置页面里 **Custom domain** 旁边会出现绿色勾选,同时建议勾选 **Enforce HTTPS**(GitHub会自动免费签发SSL证书)

## 还需要补充的真实信息(目前是占位符,上线前替换)

- 页脚的邮箱、电话(中文版还多了微信号占位符)
- 实际合作医院名称(如已谈成,可以加入"为什么选择中国"或单独做一个板块)
- 表单目前是纯展示,没有接收后端——需要接入类似 Formspree、EmailJS 这类免费表单服务,或自建后端,否则填了也收不到
