#   openwrt-themedog
    基于 Openwrt21 JavascriptApi 的主题
    前端使用 vue3 Typescript 配合  iframe 实现的可视化主题

#  切换至别的主题后首页为空?
    themedog 会注册
        luci/luci-themedog/root/usr/share/luci/menu.d/luci-themedog.json
    文件实现注册顶级菜单。
    导致切换主题后该文件依旧存在。目前暂无发现相关钩子能触发动作。
    所以如果不想使用 themedog 主题， 可在切换主题后使用命令
    opkg remove luci-themedog 
    把主题卸载即可
    

##  自定义图标?
    根据 菜单名称 调用图标
        luci/luci-themedog/htdocs/luci-static/dog/icons
        app-icon.png 为默认占位图标
    其余的请根据喜好 更换/添加/删除

##  窗口样式不清晰?
    默认使用了 Openwrt21_bootstrap 的 cascade.css 进行了微修改
    对此不满意可替换:
        luci/luci-themedog/htdocs/luci-static/themedog/css/cascade.css
    进行更新覆盖

##  背景替换?
    背景可替换:
        luci/luci-themedog/htdocs/luci-static/themedog/image/bg.gif
    进行更新覆盖

##  构建:
    make -j16 V=s package/openwrt-themedog/luci/luci-themedog/compile
## 演示:
![](./demo/0.png)
![](./demo/1.png)
![](./demo/2.png)
![](./demo/3.png)
