# accumulation-animation

## 简介

为你的数据添加动态递增效果😀！

## 文档

### 入门

#### 安装

```bash
npm i accumulation-animation
```

#### 使用

🚀你可以在Dom任何绑定数据的地方使用它

这里拿element的表格举例📕：

1、引入组件

全局引用(main.js中)

```javascript
import accumulationAnimation from 'accumulation-animation';

Vue.use(accumulationAnimation)
```

按需加载

```javascript
import { accumulationAnimation } from 'accumulation-animation'

components: {
  accumulationAnimation
},
```



2、挂载组件

```vue
      <el-table-column prop="percentage" label="比例" width="180" align="center">
        <template slot-scope="scope" style="color: #42b983">
          <accumulationAnimation
            :style="{color: 'red'}"
            :number="Number(scope.row.percentage)"
            :max-number="100"
            :unit="'%'"
          />
        </template>
      </el-table-column>
```

### 选项

#### number(必选)

- **类型**：`Number`
- **默认值**：`0`
- **描述**：需要添加效果的数据值

#### speed(可选)

- **类型**：`Number?`
- **默认值**：`20`
- **描述**：设置基准数据增速

#### maxNumber(可选)

- **类型**：`Number?`
- **默认值**：`0`
- **描述**：对照数据组**最大值**；默认所有数据增速一致(不同时结束)，当需要控制动态增速使数据递增动效同时结束时，可设置此选项

#### unit(可选)

- **类型**：`String?`
- **默认值**：`""`
- **描述**：数据单位(可以添加任何你想展示的值)

## 作者

QQ：1415580200