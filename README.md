# 使用说明

注意：
- 以下所有的title都需要加英文双引号""
- git需要两个仓库，一个为此仓库用来写博客，一个为静态文件提交的仓库，即github pages的仓库，在`_config.yml`的`repo`中修改配置链接

### 博客
``` bash
npm run write -- title
```

### 草稿
``` bash
# 新建草稿
npm run draft -- title

# 发布草稿
npm run draft:publish -- title
```

### 预览
``` bash
# 常规预览
npm run preview

# 可预览草稿
npm run preview:draft
```

### 发布
``` bash
npm run deploy
```


# 图片使用
hexo中插入图片有两种方式：
1. 所有博客图片统一放在source/images下，markdown中通过传统markdown语法代码引入
   ``` markdown
   ![logo](../images/logo-200x200.jpg)
   ```
2. 开启`post_asset_folder`配置项
   每次创建博客markdown的时候，都会在markdown同目录下创建同名文件夹。比如博客名为A，也会创建文件夹A。
   博客中用到的图片可以放到该博客对应的文件夹中。但是在markdown中引入图片的方式需要通过如下：
   ``` markdown
   {% asset_img logo-200x200.jpg image name %}
   ```

考虑到：
- 大部分博客所需图片较少，如果每篇博客都会创建一个文件夹，长期下来会存在大量空文件夹
- 第二种方法需要特殊的语法，与markdown语法不兼容，预览markdown时不直观

所以默认采用第一种方式。
