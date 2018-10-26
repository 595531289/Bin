# Bin
OC调用C++
首先新建一个c++文件,命名为CPPHello
以下是C++的hpp文件
#ifndef CPPClass_hpp
#define CPPClass_hpp 
#include <stdio.h>
class CPPHello{   
public:
    static void sayHello(); 
    static void sayGoodBye();
};
#endif /* CPPClass_hpp */
--------------------- 分割线--------
以下是C++的cpp文件

#include "CPPClass.hpp"
 
void CPPHello::sayHello(){ 
    printf("OC调用了C++");
}
void CPPHello::sayGoodBye(){
    objcSayHello();//这是调用OC的方法
}
--------------------- 分割线--------
我们在viewcontroller中调用
首先引用#import “CPPClass.hpp”
在按钮“TestOC”的点击方法中调用  CPPHello::sayHello();
在按钮"TestC++"的点击方法中调用 CPPHello::sayGoodBye();

C++调用OC
创建一个NSObject类，命名OCClass，写一个打印方法
void objcSayHello(){
    NSLog(@"C++ 调用 OC");
}
然后在CPPClass类中的sayHello方法中调用，
首先导入头文件#include "OCClass.h"
运行会报错，这是因为OC可以兼容C,C++,但是C++不能完全兼容OC，
所以如果要引用OC文件的话，OC的.h文件中不能有OC里面的语法，
将OCClass.h的内容全部删除
只写一句void objcSayHello();
然后在OCClass.m文件，将后缀改为.mm

具体操作还是要看一下demo




