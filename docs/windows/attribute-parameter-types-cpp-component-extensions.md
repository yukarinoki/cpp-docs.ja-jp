---
title: 属性パラメーター型 (C++ コンポーネント拡張) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79d89eec82725b28bdbe43f08ac2c05cdb889f6e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466970"
---
# <a name="attribute-parameter-types--c-component-extensions"></a>属性パラメーターの型 (C++ コンポーネント拡張)
属性に渡される値は、コンパイル時にコンパイラに判明する必要があります。  次の種類の属性のパラメーターができます。  
  
-   **bool**  
  
-   **char**、 **unsigned char**  
  
-   **short**, **unsigned short**  
  
-   **int**、**符号なし int**  
  
-   **長い**、 **unsigned long**  
  
-   **_ _int64**、**符号なし _ _int64**  
  
-   **float**、 **double**  
  
-   **wchar_t**  
  
-   `char*` または `wchar_t*` または `System::String*`  
  
-   `System::Type ^`  
  
-   `System::Object ^`  
  
-   **enum**  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```cpp  
// attribute_parameter_types.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct AStruct {};  
  
[AttributeUsage(AttributeTargets::ReturnValue)]  
ref struct Attr : public Attribute {  
   Attr(AStruct ^ i){}  
   Attr(bool i){}  
   Attr(){}  
};  
  
ref struct MyStruct {  
   static AStruct ^ x = gcnew AStruct;  
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104  
   [returnvalue:Attr] int Test2() { return 0; }   // OK  
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK  
};  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 属性を指定するときにすべての名前のない (位置) 引数、名前付き引数の前にする必要があります。  
  
### <a name="code"></a>コード  
  
```cpp  
// extending_metadata_c.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // No arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // Named argument  
  
[MyAttr(123)]   
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]   
ref class ClassD {};   // Positional and named  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 属性のパラメーターは、前の型の 1 次元の配列を指定できます。  
  
### <a name="code"></a>コード  
  
```cpp  
// extending_metadata_d.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="see-also"></a>関連項目  
 [ユーザー定義の属性](../windows/user-defined-attributes-cpp-component-extensions.md)