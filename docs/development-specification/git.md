## git工作流 {docsify-ignore}
包括分支使用、commit规范及tag规范

### branch

- **master** [主分支]
- **staging** [预发分支]
- **qa**  [测试分支]
- **feature/***  [功能分支]
- **bugfix/***  [bug修复分支]

### commit
- 格式：`<type>: <subject>`；
- type：代表某次提交的类型，比如是修复一个bug还是增加一个新的feature；
- subject：描述主要变更内容，比如新增commit提交规范，英文均为小写字母；
- 应尽可能以功能模块颗粒化commit，杜绝一次性提交；
- 开源项目必须英文，内部项目尽可能英文。

type类型如下：

type | 说明
:-- | :--
feature | 新功能
fix | 修复bug
docs | 仅仅修改了文档，比如README, CHANGELOG, CONTRIBUTE等等
style | 仅仅修改了空格、格式缩进、逗号等等，不改变代码逻辑
refactor | 代码重构，没有加新功能或者修复bug
perf | 优化相关，比如提升性能、体验
test | 测试用例，包括单元测试、集成测试等
chore | 改变构建流程、或者增加依赖库、工具等
revert | 回滚到上一个版本

```shell
git commit -m 'feature: add commit message spcification'
```

### tag
- Tag name：版本号v1.0.1
- Create from：master
- Message：版本简要描述
- Release notes：以下面的markdown形式，这些点都是方便后续维护和问题追踪

```markdown
### changelog
1. 增加分支规范
2. 增加commit message规范

### docs
- [需求文档](https://booheefe.github.io/docs)
- [设计稿](https://booheefe.github.io/docs)

### authors
- 吴胜斌
```

### git flow
步骤：
- 第一步：根据需求，从远程`master`拉出新的`feature/*`或`bugfix/*`分支；
- 第二步：每一个功能点完成之后进行`commit`，如果是多人协作，在`push`推到远程仓之前应进行`pull rebase`操作: `git pull origin feature/* --rebase`；
- 第二步：功能开发完成后将`feature/*`或`bugfix/*`合并进`qa`分支，发布代码到测试环境供测试同学测试；
- 第三步：`qa`测试完成，再将`feature/*`或`bugfix/*`合并进`staging`分支，发布到预发环境测试；
- 第四步：全部测试通过，将`feature/*`或`bugfix/*`合并进`master`分支，并删除`feature/*`或`bugfix/*`；
- 第五步：请运维同学发布到正式环境后，再请产品、测试同学进行线上验证，没问题后打`tag`，有问题回到第一步。

提示：
- 小程序开发，由于有自己的开发、测试机制，并且比较简单，`qa`和`staging`分支环节都可以省去；
- 有的公司可能没有预发环境，第三步可以省去，我们一般在跟第三方合作时会用到