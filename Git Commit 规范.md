AngularJS团队的[AngularJS Git Commit Message Conventions](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines)是目前使用最广的规范，清晰的提交信息会使我们很容易追踪定位项目历史。

使用最多的格式规范如下：
>     type(scope?): subject
>     body?
>     footer?

---

### git commit 引导
[Commitizen](https://github.com/commitizen/cz-cli)将提示和引导我们在提交时填写所需的提交字段。

在提交时执行`git cz`代替`git commit`：
![Image](https://user-gold-cdn.xitu.io/2018/9/30/16628b2f47162225?w=557&h=300&f=png&s=64464)

---

### git commit 校验
[Commitlint](http://marionebl.github.io/commitlint/#/)能够帮助团队遵守git commit规范，当提交信息不符合格式规范时，提交钩子运行后拒绝提交。

使用时只需安装依赖：`npm install --save-dev commitizen @commitlint/cli @commitlint/config-conventional`。

在`.commitlintrc.yml`中配置规则[Rules](http://marionebl.github.io/commitlint/#/reference-rules)。
并在package.json中添加：
```
"scripts": {
  "commitmsg": "commitlint -E GIT_PARAMS"
}
"husky": {
  "hooks": {
    "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
  }
}
```
效果如下：
![Image](https://commitlint.js.org/assets/commitlint.svg)

*Enjoy* 😉.
