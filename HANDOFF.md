# 科研与项目成果展示页改版

## 1. 当前目标
将现有 Research 简历页改为科研与项目成果展示页。八项成果的正文、职责、奖项、仓库链接和新布局已完成且通过本地验证；正在准备 v1.10.4 发布。旧嵌套副本不在修改范围。

## 2. 完成条件
八项成果和九个项目仓库链接完整；QDepth-VLA 不编造链接；论文明确为 AI and Energy 在投；桌面与手机无横向溢出。推送 Research，并在 Home/Site 同步同版本更新日志，验证三站部署。

## 3. 已确认事实
现有 Research GitHub 仓库为 GPDdev/research.hachile.org，main 分支，GitHub Pages 使用 legacy 分支发布，自定义域名 research.hachile.org，HTTPS 已开启。新工作副本为约定的独立目录，原嵌套副本保持不变。

## 4. 相关文件与命令
- D:\Desktop\hachile-workspace\research.hachile.org\index.html：八项成果静态 HTML。
- assets/research.css：响应式布局、目录与打印样式。
- .nojekyll、CNAME：沿用原部署文件。
- Home 的 tools/build-en.mjs 生成英文和手机页。
- Home 现有 assets/app.js、assets/home.css 为任务外未提交改动，不纳入本次提交。
- 本地预览：python -m http.server 18777 --bind 127.0.0.1。隔离 Edge/Playwright 已验证 1440、768、390、320 像素宽度：八项成果、九个仓库链接、全部锚点正确，无横向溢出和控制台错误。缺少 favicon 的首次错误已用 assets/research-mark.svg 修正，复测通过。
- Home/Site 本次同步版本为 v1.10.4；Home 的英文与手机版需执行 node tools/build-en.mjs 重新生成。

## 5. 已否决方案
不新增框架和运行时依赖；不将论文展示为已发表；不把相关模拟器称为论文正式代码；不编造 QDepth-VLA 仓库入口。

## 6. 风险与待确认项
项目结果和奖项依据用户提供文本，未独立核验。项目链接可核对是否与输入一致；私有或暂不可访问的仓库不擅自删除。

## 7. 下一步动作
执行 Home 的 node tools/build-en.mjs 和三个仓库的 git diff --check，确认仅提交本次改动后推送，核对 Pages 构建提交及线上页面。
