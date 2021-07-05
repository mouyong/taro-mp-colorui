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
+    "patch": "sh -c './node_modules/.bin/patch-package mp-colorui'",
+    "postinstall": "sh -c './node_modules/.bin/patch-package'",
    ...
  },
}
```

## 需要修复 node_modules/mp-colorui 的代码时

1. 修复 `node_modules/mp-colorui/dist/index.esm.js` 文件中的相关错误
2. 修复 `node_modules/mp-colorui/lib/src/` 目录下的相关错误
3. 生成补丁 `yarn patch`
4. 更新 issue：https://github.com/yinLiangDream/mp-colorui/issues/113 对应的补丁内容。补丁内容为 `mp-colorui+1.0.0-beta.1.patch` 的全部内容

## 安装 taro-utils

前往查看：https://github.com/mouyong/taro-utils


## 开发

```shell
taro build --type h5 --watch
```
