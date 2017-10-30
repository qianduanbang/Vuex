## Vuex

### Vuex是什么？

		Vuex类似Redux的状态管理器，用来管理Vue的所有组件状态。

### 为什么使用Vuex？

		当你打算开发大型单页应用（SPA），会出现多个视图组件依赖同一个状态，来自不同视图的行为需要变更同一个状态
		
		遇到以上情况时候，你就应该考虑使用Vuex了，它能把组件的共享状态抽取出来，当做一个全局单例模式进行管理
		
		这样不管你在何处改变状态，都会通知使用该状态的组件做出相应修改

### 在Vue组件使用Vuex

		如果希望Vuex状态更新，相应的Vue组件也得到更新，最简单的方法就是在Vue的computed（计算属性）获取state

### State

		State负责存储整个应用的状态数据，一般需要在使用的时候在跟节点注入store对象
		
		后期就可以使用this.$store.state直接获取状态

### Actions

		Actions也可以用于改变状态，不过是通过触发mutation实现的
		
		重要的是可以包含异步操作、判断、流程控制，其辅助函数是mapActions

### Mutations

		Mutations的中文意思是“变化”，利用它可以更改状态，本质就是用来处理数据的函数，其接收唯一参数值state

### Getters

		有些状态需要做二次处理，就可以使用getters，其接收唯一参数值state

### Vuex的原理和使用方法

		单向数据流
			一个应用可以看作是由三部分组成: View,Actions,State,
			数据的流动也是从 View => Actions => State => View
			以此达到数据的单向流动。但是项目较大的，组件嵌套过多的时候，
			多组件共享同一个State会在数据传递时出现很多问题，Vuex就是为了解决这些问题而产生的
		
		Vuex可以被看作项目中所有组件的数据中心，我们将所有组件中共享的State抽离出来，
		任何组件都可以访问和操作我们的数据中心。
		
		Vuex的组成：
		
			一个实例化的Vuex.Store由state,mutations和actions三个属性组成：
				state中保存着共有数据，改变state中的数据只有通过mutations中的方法，
				并且mutations中的方法必须是同步的，如果要写异步的方法，
				需要写在actions中，并通过commit到mutations中进行state数据的更改。
