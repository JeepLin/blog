##单例模式
###一、模式描述:
确保一个类仅有一个唯一的实例，并且提供一个全局的访问点

###二、环境及问题:
当使用这个类的时候，只需要该类只有一个实例存在 <br />
需要解决独生子女的问题 <br />
比如打印机进程的管理对象, 配置文件的管理对象等 <br />

###三、解决方案:
1、首先将构造方法私有化，将构造方法改为private，屏蔽通过直接实例化的形式来访问<br />
2、控制全局只有一个类的实例(static) <br />
3、提供一个可以获得实例方法，并且需要保证没有获取的实例都是同一个<br />

###四、代码

####Go语言版本
```
//singleton.go
package singleton

//使用小写私有变量保存唯一实例
var one *singleton

type singleton struct{}

func GetInstance() *singleton {
	if one == nil {
		one = &singleton{}
	}
	return one
}
```

####C++版本
```
class Singleton
{
	//使用静态私有全局变量保存唯一实例
	private static Singleton one;
	
	//私有化构造函数
	private Singleton(){
	}
	
	//保证只会实例化一次
	public static Singleton GetInstance(){
		if (null == one){
			one = new Singleton();
		}
		return one;
	}
}
```

2018-05-14 于深圳

