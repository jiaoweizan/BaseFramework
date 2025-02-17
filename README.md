
# 目录
* [编码记录](commonlibrary/README_CodingHistory.md)<br>

* [详细功能使用说明](commonlibrary/README_FunctionDetails.md)<br>

#  配置
######  Step 1. JitPack库添加到你的构建文件

  ```  
  allprojects {
	repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
###### Step 2. 添加相关依赖
  ``` 
   apply plugin: 'com.android.application'
   apply plugin: 'org.greenrobot.greendao' // apply plugin
   
    ..........
    android {    
            defaultConfig {
                 ..........
              //在app 和 mode 的build.gradle 下的defaultConfig里面添加

                ndk {
                    abiFilters "armeabi"    //添加ndk支持
                }        
                 ..........
            }  
            //所有使用到网络请求的mode都要添加        
            compileOptions {
                sourceCompatibility JavaVersion.VERSION_1_8
                targetCompatibility JavaVersion.VERSION_1_8
             }   
           greendao {
                schemaVersion 1
                daoPackage 'XXXXX'//greendao //路径
                targetGenDir 'src/main/java'//保存到java代码路径
            }
             }
           dependencies {
               implementation 'com.github.ZhetengDashen:BaseFramework:2.0.7'
            }  
 ``` 
######  
 
###### 添加greendao插件
   ``` 
   // 在 Project的build.gradle 文件中添加:
        buildscript {
            repositories {
                jcenter()
                mavenCentral() // add repository
            }
            dependencies {
                classpath 'com.android.tools.build:gradle:3.1.2'
                classpath 'org.greenrobot:greendao-gradle-plugin:3.2.2' // add plugin
            }
        }
   ``` 
` *注  每创建一个Bean类就需要创建一个BeanManager，用于管理数据库中的表。`  <br/>
       `BeanManager 需要继承 BaseDbBeanManager .`   
   ```   
//例子
public class UnitBeanManager extends BaseDbBeanManager<UnitBean,String> {
  public UnitBeanManager(AbstractDao dao) {
        super(dao);
    }
}
 
   ``` 
## Library
+ <strong> [ARouter](https://github.com/alibaba/ARouter)<br>
+ <strong> [FastJson](https://github.com/alibaba/fastjson)<br>
+ <strong> [Gson](https://github.com/google/gson)<br>
+ <strong> [OkHttp](https://github.com/square/okhttp)<br>
+ <strong> [AVLoadingIndicatorView](https://github.com/81813780/AVLoadingIndicatorView)<br>
+ <strong> [EventBus](https://github.com/greenrobot/EventBus)<br>
+ <strong> [glide](https://github.com/bumptech/glide)<br>
+ <strong> [picasso](https://github.com/square/picasso)<br>
+ <strong> [BaseRecyclerViewAdapterHelper](https://github.com/CymChad/BaseRecyclerViewAdapterHelper)<br> 
+ <strong> [LogUtils](https://github.com/pengwei1024/LogUtils)<br>
+ <strong> [RxPermissions](https://github.com/tbruyelle/RxPermissions)<br>
+ <strong> [Android-PickerView](https://github.com/Bigkoo/Android-PickerView)<br>
+ <strong> [PictureSelector](https://github.com/LuckSiege/PictureSelector)<br>
+ <strong> [Luban](https://github.com/Curzibn/Luban)<br>
+ <strong> [greendao](https://github.com/greenrobot/greenDAO)<br>
+ <strong> [GreenDaoUpgradeHelper](https://github.com/yuweiguocn/GreenDaoUpgradeHelper)<br>
+ <strong> [RxJava2](https://github.com/ReactiveX/RxJava)<br>
+ <strong> [RxAndroid](https://github.com/amitshekhariitbhu/RxJava2-Android-Samples)<br>
+ <strong> [RxLifecycle](https://github.com/trello/RxLifecycle)<br>
+ <strong> [Retrofit2](https://square.github.io/retrofit/)<br>   
   
# 注
> `项目修改请补充文件说明。`<br/>
> `第三方类库请注明出处地址或参考文档地址。`


    
       