## vue的生命周期

- beforeCreate（创建前）

数据观测和初始化事件还没开始

- created（创建后）

完成数据观察，属性和方法的运算，初始化事件，el属性还没有显示出来

- beforeMount（载入前）

相关的render函数首次被调用，实例已完成以下的配置：编译模版，把data里面的数据和模版生成html，此时还没有挂在html到页面上。

- mounted（载入后）

el被新创建的vm.el替换，并挂载在实例上去之后调用。实例已经完成以下配置：用上面编译好的html内容替换el属性指向的DOM对象。完成模版中的html渲染到html页面中，此过程进行ajax交互。

- beforeUpdate（更新前）

在数据更新之前调用，发生在虚拟DOM重新渲染和打补丁之前。可以在该钩子中进一步的更改状态，不会触发附加的重渲染过程。

- update（更新后）

由于数据更改导致的虚拟DOM重新渲染和打补丁之后调用。调用时，DOM已经更新，所以可以执行依赖于DOM的操作。然而在大多数情况下，应该避免在此期间更改状态，因为这可能会导致更新无限循环。该狗仔在服务器端渲染的期间不被调用。

- beforeDestroy（销毁前）

在实例销毁之前调用。实例仍然完全可用。

- destroy（销毁后）

在实例销毁之后调用。调用后，所有的事件监听都会被移除，所有的子实例也会被销毁。该钩子在服务器端渲染前不被调用


### 什么是vue生命周期

vue实例从创建到销毁的过程，就是生命周期。

从开始创建、初始化数据、编译模版、挂载DOM->渲染、更新->渲染、销毁等一系列过程，称之为vue的生命周期。

### vue生命周期的作用是什么

它的生命周期中有很多事件钩子函数，让我们在控制整个Vue实例的过程时更容易形成好的逻辑。

### 生命周期总共有几个阶段

总共有8个阶段：创建前/创建后，载入前/后，更新前/后，销毁前/后。

### 第一次页面加载会触发哪几个钩子

会触发beforeCreate, created, beforeMount, mounted这四个

### DOM渲染在哪个周期就已经完成

DOM渲染在mounted中就已经完成了