# 作战方局部栈

## 概念

现在每个作战方可以独立保存一些栈。  
使用栈基于 **索引值**，**索引值** 可以是 0 ~ 10000 的任意整数。  
未处理存档。

## 入栈 <主动>

位于 `rulesmd.ini`：

```ini
[SomeBuffType]
Effect.Type=StackPush
```

将挂载此 Buff 的单位推入指定的栈内。

### 注意

* 只有进入 `生效状态` 时，单位才会被推入栈内。
* 单位被推入栈内后，会立刻进入 `结束状态`（即不会停留在 `生效状态`）。
* 当 Buff 被移除或挂载 Buff 的单位死亡，单位会被从栈内移除。

### 效果强度值转换：0 项参数

### 效果种类相关属性

位于 `rulesmd.ini`：

```ini
[SomeBuffType]
; 效果种类相关属性
Effect.ExtraCodeA=0                             ; 整数 , 用来决定栈的索引 , 取值范围 : 0 ~ 10000 , 无效值默认为 0 , 默认值是 0
Effect.Source=no                                ; yes/no , 决定栈被存储在哪一作战方 , 默认值是 no
                                                ; yes = 栈存储在 Buff 来源的作战方
                                                ; no = 栈存储在挂载此 Buff 的单位的作战方
```

### 广播与监听相关属性

不支持广播或监听。

### 数值显示相关属性

不支持数值显示。



## 栈顶挂载 Buff <主动>

位于 `rulesmd.ini`：

```ini
[SomeBuffType]
Effect.Type=StackTop
```

给指定的栈的栈顶单位挂载 Buff 。

### 注意

* 该 Buff 不会自动将栈内的单位弹出。
* Buff 挂载生效后，会立刻进入 `结束状态`（即不会停留在 `生效状态`）。

### 效果强度值转换：0 项参数

### 效果种类相关属性

位于 `rulesmd.ini`：

```ini
[SomeBuffType]
; 效果种类相关属性
Effect.AcceptBuffs=                             ; Buff 列表 , 挂载这些 Buff , 没设置就不挂载
Effect.ExtraCodeA=0                             ; 整数 , 用来决定栈的索引 , 取值范围 : 0 ~ 10000 , 无效值默认为 0 , 默认值是 0
Effect.Source=no                                ; yes/no , 决定栈被存储在哪一作战方 , 默认值是 no
                                                ; yes = 栈存储在 Buff 来源的作战方
                                                ; no = 栈存储在挂载此 Buff 的单位的作战方
```

### 广播与监听相关属性

不支持广播或监听。

### 数值显示相关属性

不支持数值显示。




## 出栈 <主动>

位于 `rulesmd.ini`：

```ini
[SomeBuffType]
Effect.Type=StackPop
```

将指定的栈的栈顶单位弹出，不做任何处理。

### 注意

* 该 Buff 不会自动将栈顶的单位拥有的入栈 Buff 结束，谨慎使用。

### 效果强度值转换：0 项参数

### 效果种类相关属性

位于 `rulesmd.ini`：

```ini
[SomeBuffType]
; 效果种类相关属性
Effect.ExtraCodeA=0                             ; 整数 , 用来决定栈的索引 , 取值范围 : 0 ~ 10000 , 无效值默认为 0 , 默认值是 0
Effect.Source=no                                ; yes/no , 决定栈被存储在哪一作战方 , 默认值是 no
                                                ; yes = 栈存储在 Buff 来源的作战方
                                                ; no = 栈存储在挂载此 Buff 的单位的作战方
```

### 广播与监听相关属性

不支持广播或监听。

### 数值显示相关属性

不支持数值显示。
