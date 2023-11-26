# Koha 手册（zh_CN）翻译

## 目录结构
```
koha-manual-i18n/ (git clone https://gitlab.com/koha-community/koha-manual-i18n.git)
  |---koha-manual/ (git clone https://gitlab.com/koha-community/koha-manual.git)
     |---locales/ (git clone https://github.com/KohaILS/manual-zh-cn.git)
     |---icons/
     |---public/
     |---source/
     |---README
     |---Makefile
     |---CONTRIBUTING.md
     |---mappings.pl
  |---lib/
  |---README
  |---update-po.pl
  |---weblate-sync.pl

manual/
  |--- docs/
     |---about.html
     ...
  |--- README
```
说明：koha-manual-i18n 和 manual 属于同级目录。koha-manual-i18n/koha-manual 为手册的仓库（https://gitlab.com/koha-community/koha-manual），koha-manual-i18n/koha-manual/locales/zh_CN 为自己维护的简体中文 Koha 手册资源文件，通过拉取获取最新翻译文件（https://github.com/KohaILS/manual-zh-cn），然后通过 make html 生成最新手册，然后将其复制到手册的仓库，推送至服务器远端。

## 构建手册资源库

### 复刻最新的手册资源库
```
git clone https://gitlab.com/koha-community/koha-manual-i18n.git
cd koha-manual-i18n
git clone https://gitlab.com/koha-community/koha-manual.git
cd koha-manual
git clone https://githab.com/KohaILS/manual-zh-cn.git locales
```

### 生成简体中文手册并复制
```
make -e SPHINXOPTS="-D language='zh_CN'" html
cp build/html/* ../../manual/docs/
```

### 推送至手册远端服务器

https://github.com/KohaILS/manual

通过浏览器访问 https://manual.koha-ils.cn

本文件来自 https://gitlab.com/koha-community/koha-manual-l10n 的繁体。
