# Next搭建博客问题记录

> 用于记录搭建博客时遇到的问题以及解决过程

## 1.引入emotion

`Npm run dev `时，Next-env.d.ts文件会自动回到初始状态，所以添加一个global.d.ts

```tsx
/// <reference types="@emotion/react/types/css-prop" />
```

如何配置Emition

首先:npm install next@latest安装至最新版，目前只有最新版支持Emotion，css in js，然后安装`npm i @emotion/react , npm i @emotion/babel-plugin  `

Next.config.js文件配置，细节参考https://nextjs.org/docs/architecture/nextjs-compiler#emotion

```js
/** @type {import('next').NextConfig} */
const nextConfig = {
  compiler:{
    emotion:true
  }
};
export default nextConfig;
```

## 2.emotion使用

嵌套判断都是非常方便的，支持选择器，也支持style的写法，可以用于覆盖一些组件库的样式

注意这里使用的是**@emotion/react**而不是**@emotion/css**，这两个的区别后面会提到

```tsx
<div
  css={[
    flag && {
      ".Number": {
        backgroundColor: "powderblue",
      },
    },
    { color: "red" },
  ]}
  >
  hello的Layout<span className="Number">123</span>
</div>
```

## 3.@emotion/react和@emotion/css的区别

最大的区别返回结果，一个是对象一个是样式字符串

```tsx
import { css } from "@emotion/react";
const styleTest = css({
  backgroundColor: "yellowgreen",
});
const styleTest: SerializedStyles
```

![image-20240421015244644](https://gitee.com/ding_wei_wu/img-path/raw/master/img/image-20240421015244644.png)

@emotion/react生成的样式对象不能直接放到className中使用（在tailwindcss中），而@emotion/css生成的对象可以直接放到className中使用，并且样式生效

![image-20240421022820423](https://gitee.com/ding_wei_wu/img-path/raw/master/img/image-20240421022820423.png)

所以可以混着用，向这样，怎么方便怎么来

![image-20240421022527745](https://gitee.com/ding_wei_wu/img-path/raw/master/img/image-20240421022527745.png)

![image-20240421022714253](https://gitee.com/ding_wei_wu/img-path/raw/master/img/image-20240421022714253.png)