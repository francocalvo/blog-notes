---
title: Dotfiles
geekdocCollapseSection: true
---

<div class="hidden">
# Contents

- [Descripción](#Descripción)
  - [Caracteristicas](#Descripción#Caracteristicas)
    - [Plugins vim](#Descripción#Caracteristicas#Plugins vim)
  - [Por hacer](#Descripción#Por hacer)
  - [Recursos](#Descripción#Recursos)

</div>

# Descripción

{{<toc>}}

Estos son los archivos necesarios para replicar mi configuración en MacOS.
En general, excepto por yabai y skhd, que pueden ser reemplazados por un WM 
como i3-gaps o bpwm en Linux, todos los archivos deberían ser compatibles con
cualquier sistema Unix.

Todo lo publicado en esta página fue escrito con [vimwiki](https://github.com/vimwiki/vimwiki) y renderizado por [Hugo](www.gohugo.io).

*Repositorio:* [Github](https://github.com/francocalvo/dotfiles)




## Caracteristicas

- Configuración extensible en Lua de Neovim.
- Configuración de Vimwiki y Hugo para publicar notas.
- Configuración de terminal kitty.
- Especifico MacOS: emulación de i3-gaps con skhd y yabai.

### Plugins vim

Los plugins utilizados en vim son:

{{< expand "Plugins" >}}
- wbthomason/packer.nvim
- nvim-lua/popup.nvim
- nvim-lua/plenary.nvim
- windwp/nvim-autopairs
- numToStr/Comment.nvim
- kyazdani42/nvim-web-devicons
- kyazdani42/nvim-tree.lua
- akinsho/bufferline.nvim
- moll/vim-bbye
- nvim-lualine/lualine.nvim
- akinsho/toggleterm.nvim
- ahmedkhalf/project.nvim
- lewis6991/impatient.nvim
- lukas-reineke/indent-blankline.nvim
- goolord/alpha-nvim
- antoinemadec/FixCursorHold.nvim
- folke/which-key.nvim
- shaunsingh/nord.nvim
- dracula/vim
- lunarvim/darkplus.nvim
- hrsh7th/nvim-cmp
- hrsh7th/cmp-buffer
- hrsh7th/cmp-path
- hrsh7th/cmp-cmdline
- saadparwaiz1/cmp_luasnip
- hrsh7th/cmp-nvim-lsp
- L3MON4D3/LuaSnip
- rafamadriz/friendly-snippets
- neovim/nvim-lspconfig
- williamboman/nvim-lsp-installer
- tamago324/nlsp-settings.nvim
- jose-elias-alvarez/null-ls.nvim
- nvim-telescope/telescope.nvim
- nvim-treesitter/nvim-treesitter
- JoosepAlviste/nvim-ts-context-commentstring
- lewis6991/gitsigns.nvim
- vimwiki/vimwiki
{{< /expand >}}

## Por hacer


* [ ] Renderizar imagenes desde vim. (ver este [plugin](https://github.com/ekickx/clipboard-image.nvim))
* [ ] Pasar configuración de vimwiki a vimwiki.lua.
* [ ] Optimizar pipeline de Drone.
* [X] Lograr autosincronización o autopublicación.
* [X] Publicar archivos en GitHub. 
* [X] Crear un index por materia.
* [X] Arreglar problema con Luasnip. ([#161 Luasnip](https://github.com/L3MON4D3/LuaSnip/issues/161))
* [X] Agregar configuraciones a whichkey. 
  * [X] Agregar abrir default wiki.
  * [X] Agregar manipulación de archivo.
  * [X] Corregir bug en back-links.
* [X] Agregar diccionario en español. ([#2804 de neovim](https://github.com/neovim/neovim/issues/2804))
* [X] Agregar opción para colapsar secciones. ([#243 de hugo-geekdoc](https://github.com/thegeeklab/hugo-geekdoc/issues/243))


## Recursos

Para la configuración de esto se usaron las siguientes referencias

- El [repositorio](https://github.com/LunarVim/Neovim-from-scratch) de Chris@Machine, acompañado de sus videos.
- [Documentacion](https://gohugo.io/documentation/) d Hugo.
- [Documentacion](https://geekdocs.de/usage/getting-started/) de Geekdocs.
