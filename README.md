<p align="center">
  <a href ="##"><img alt="Omi" src="http://images2015.cnblogs.com/blog/105416/201701/105416-20170120114244046-622856943.png"></a>
</p>

<p align="center">
Open and modern framework for building user interfaces.
</p>

---

## Omi相关

* 如果想使用Omi框架，请阅读  [Omi使用文档](https://github.com/AlloyTeam/Omi/tree/master/docs#omi使用文档)
* 如果想一起开发完善Omi框架，有更好的解决方案或者思路，请阅读  [从零一步步打造web组件化框架Omi](https://github.com/AlloyTeam/Omi/tree/master/docs#从零一步步打造web组件化框架omi)
* 如果你有Omi相关的问题可以[New issue](https://github.com/AlloyTeam/Omi/issues/new)
* 如果想更加方便的交流关于Omi的一切可以加入QQ的Omi交流群(256426170):

![qq](./asset/omi_group.png)

## 通过npm安装 

``` js
npm install omi
```

## Hello World

```js
class Hello extends Omi.Component {
    constructor(data) {
        super(data);
    }
    style () {
        return  `
            h1{
                cursor:pointer;
            }
         `;
    }
    handleClick(target, evt){
        alert(target.innerHTML);
    }
    render() {
        return  `
        <div>
            <h1 onclick="handleClick(this, event)">Hello ,{{name}}!</h1>
        </div>
        `;

    }
}

Omi.render(new Hello({ name : "Omi" }),"body");
```

你可以使用Omi.makeHTML来生成组件标签用于嵌套。
```js
    Omi.makeHTML(Hello);
```
那么你就在其他组件中使用，并且通过data-*的方式可以给组件传参，如：
```js
  ...
  render() {
        return  `
        <div>
            <div>Test</div>
            <Hello data-name="Omi" />
        </div>
        `;
    }
    ...
```

你可以使用 [webpack](https://webpack.github.io/) + [babel](http://babeljs.io/)，让你立刻马上使用ES6+来编写你的web程序。你只需要在webpack配置的module设置好[babel-loader](https://github.com/babel/babel-loader)便可。

 当然Omi没有抛弃ES5的用户。你可以使用ES5的方式编写Omi。具体可以看这里[Hello World with ES5](https://github.com/AlloyTeam/Omi/blob/master/docs/cn_hello_world.md#hello-world-with-es5)

# License
This content is released under the [MIT](http://opensource.org/licenses/MIT) License.