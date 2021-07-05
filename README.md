## 添加 mp-colorui h5 修复 patch

```shell
git subtree add -P patches/ https://github.com/mouyong/taro-mp-colorui.git master

yarn add --dev patch-package postinstall-postinstall
yarn postinstall mp-colorui@^1.0.0-beta.1
```

## 添加 package.json scripts 执行命令

```diff
{
  ...
  "scripts": {
+    "patch": "sh -c './node_modules/.bin/patch-package mp-colorui --create-issue'",
+    "postinstall": "sh -c './node_modules/.bin/patch-package'",
    ...
  },
}
```

## 安装 taro-utils

前往查看：https://github.com/mouyong/taro-utils


## 开发

```shell
taro build --type h5 --watch
```
