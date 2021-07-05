## 添加 mp-colorui h5 修复 patch

```shell
git subtree add -P patches/ https://github.com/mouyong/taro-mp-colorui.git master

yarn add --dev patch-package postinstall-postinstall
yarn postinstall
```

## 添加 package.json scripts 执行命令

```diff package.json
{
  ...
  "scripts": {
    +"patch": "sh -c './node_modules/.bin/patch-package mp-colorui --create-issue'",
    +"postinstall": "sh -c './node_modules/.bin/patch-package'",
    ...
  },
}
```

## 开发

```shell
taro build --type h5 --watch
```
