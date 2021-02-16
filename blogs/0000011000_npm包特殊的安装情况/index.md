## 不同的包有不同版本的依赖
例如
```
-project
--packageE
---packageA@^1.x.x
--packageF
---packageA@^2.x.x
```

实际的安装情况为，packageA的一个版本（可能为1.x也可能为2.x）被提到第一级上。
```
-project
--packageA@^1.x.x
--packageE
--packageF
---packageA@^2.x.x
```

## 依赖的包有peer依赖
例如以下的依赖情况
```
project
-packageC
--packageB
---(peer)packageA
```

在安装 packageC 时，packageA会被安装(npm7)，或被提示安装（npm6）。

## 不同的包有不同版本的peer依赖
例如
```
-project
--packageB
---(peer)packageA@^1.x.x
--packageD
---(peer)packageA@^2.x.x
```

这时是无法同时安装两个版本的，也就是说无法同时使用 packageB 和 packageD。在npm7会提示冲突，在npm6会提示安装两个不同版本，但是无法安装。

## 不同的包中有同一个包的普通依赖和peer依赖
例如
```
-project
--packageB
---(peer)packageA
--packageE
---packageA
```

这时 packageA 会被提升。在 npm6 中不安装也不会提示，但还是最好进行手动安装。

### 更复杂的情况
例如
```
-project
--packageB
---(peer)packageA@1.x.x
--packageE
---packageA@1.x.x
--packageF
---packageA@2.x.x
```

npm7中， packageA@1.x.x 会被提升；package-f 内会安装 packageA@2.x.x 。
npm6中，packageA@1.x.x 不一定会被提升，最好手动进行安装。