# Tailwind响应式

> 在看Demohttps://ui.shadcn.com/blocks案例的时候发现，布局响应式非常优秀，于是学习一下
>
> 总体还是使用tailwindcsshttps://tailwindcss.com/docs/max-width

## 1.基础用法

```html
<div className="sm:py-5">media test</div>
```

```react
@media (min-width: 640px) {
  .sm\:py-5 {
    padding-top: 1.25rem/* 20px */;
    padding-bottom: 1.25rem/* 20px */;
  }
}
```

作用是width>640生效

于是就可以通过sm:控制显示与隐藏

Demo，小于640隐藏

```html
<div className="hidden sm:flex ....."></div>
```

```react
//md:
@media (min-width: 768px) {
  .md\:flex {
    display: flex;
  }
}
//当前还有xl：1280px
@media (min-width: 1280px) {
  .xl\:grid-cols-4 {
    grid-template-columns: repeat(4, minmax(0, 1fr));
  }
}
//lg:
@media (min-width: 1024px) {
  .lg\:col-span-2 {
    grid-column: span 2 / span 2;
  }
}
```

## 2.表格布局更适合响应式

看着Demo里面都是都是表格布局实现的响应式，小于640就会编程一行grid的设置无效

```html
<div className="grid gap-4 sm:grid-cols-2 md:grid-cols-4 lg:grid-cols-2 xl:grid-cols-4">
  <Card className="sm:col-span-2" x-chunk="dashboard-05-chunk-0">1 </Card>
  <Card x-chunk="dashboard-05-chunk-1">2</Card>
  <Card x-chunk="dashboard-05-chunk-2">3</Card>
</div>
```

