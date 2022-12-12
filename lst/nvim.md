# Neovim

## 优秀插件

### coc.nvim

#### lsp

##### clangd处理Makefile组织的C语音项目

clangd本身并不能“理解”Makefile，可以使用命令行工具`bear`将Makefile转换为能够理解的compile_commands.json

如果你使用譬如`make run`来编译运行项目，则可以

`bear -- make run`来创建json

注意，低版本的bear中为：

`bear make run`

然后你的clangd就可以正确“理解”项目，不再会有各自的找不到头文件等等了
