# vscode vim 键绑定设置

我发现 vscode 几乎每个操作都有对应的命令，可以绑定到键上，而且`when`表达式更是强大，可以让相同的键绑定在不同的界面中拥有不同的功能，比如`a`在编辑器界面是在当前字符后插入的意思，在文件浏览器界面就可以是新建文件的意思，大大增加了可用性。

只需要极其简单的设置，vscode 的键绑定就可以和 neovim 大佬们精心调配的一样好用，有了这个还用啥 neovim，跟完全看不懂的 lua 说拜拜吧！

下面是我正在使用的键绑定设置，主要参考对象是[AstroNvim](https://github.com/AstroNvim/AstroNvim)，但并不完全一样，比如在 AstroNvim 里，代码动作的键绑定是`<leader>la`，vscode 里自带了`ctrl+.`，我觉得 vscode 自带的这个就很好用，所以就不改了。

> 下文中的`<leader>`键指的是空格键

1. 代码跳转
   1. 转到定义 `gd`
   2. 转到引用 `gr`
   3. 转到实现 `gi`
2. lsp
   1. 代码格式化 `<leader>lf`
   2. 变量重命名 `<leader>lr`
   3. 定义速览 `K`
   4. 代码动作 `ctrl+.` vscode 自带
   5. 代码诊断 `ctrl+shift+m` vscode 自带
   6. 代码折叠 `zc` vim 插件自带
   7. 代码展开 `zo` vim 插件自带
   8. 代码全部折叠 `<leader>zc`
   9. 代码全部展开 `<leader>zo`
3. 搜索
   1. 全局搜索文件 `<leader>ff`
   2. 全局搜索文字 `<leader>fw`
   3. 全局搜索后聚焦到结果列表 `enter`
   4. 从搜索结果列表回到搜索输入框 `esc`
   5. 从搜索输入框回到编辑器 `esc`
   6. 普通搜索 `ctrl+f` vscode 自带
4. 当前编辑器
   1. 保存 `<leader>w`
   2. 关闭 `<leader>c`
   3. 退出 vscode `<leader>q`
5. 编辑器组
   1. 上一个标签页 `H`
   2. 下一个标签页 `L`
   3. 上一个标签组 `ctrl+h`
   4. 下一个标签组 `ctrl+l`
   5. 移动到上一个标签组 `<leader>H`
   6. 移动到下一个标签组 `<leader>L`
   7. 关闭组内所有标签 `<leader>gc`
   8. 缩小 `ctrl+left`
   9. 扩大 `ctrl+right`
6. 文件操作
   1. 打开文件浏览器 `<leader>e`
   2. 关闭文件浏览器 `ctrl+b` vscode 自带
   3. 在文件浏览器里上下浏览 `j` `k`
   4. 打开文件 `o` 或 `enter`
   5. 在新标签组打开文件 `O`
   6. 新建文件 `a`
   7. 新建文件夹 `A`
   8. 删除 `d`
   9. 复制 `y`
   10. 剪切 `x`
   11. 粘贴 `p`
   12. 重命名 `r`
   13. 刷新文件浏览器 `R`



要应用这些键绑定只需要两个 json 文件，都是 vscode 自带的，一个是`settings.json`，另一个是`keybindings.json`。

在 vscode 里按`ctrl+shift+p`，搜索`打开用户设置`，选中`首选项：打开用户设置 (JSON)`，就会打开`settings.json`文件。

在 vscode 里按`ctrl+shift+p`，搜索`打开键盘快捷方式`，选中`首选项：打开键盘快捷方式 (JSON)`，就会打开`keybindings.json`文件。

在做代码跳转或切换标签页等操作时，我们都是在编辑器界面的 vim 插件里，所以这些键绑定由 vim 插件管理，配置写在`settings.json`里。

而在文件浏览器界面或搜索结果界面时，我们不是在 vim 插件里，vim 就管不了这里了，这些键绑定由 vscode 自身管理，配置写在`keybindings.json`里。

你可以将我提供的 json 文件里的内容手动复制出来，手动粘贴到你自己的配置文件里，一保存，好用的键绑定立刻就拥有了。

