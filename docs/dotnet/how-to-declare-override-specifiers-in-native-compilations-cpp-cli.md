---
title: '方法: オーバーライド指定子を宣言 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8119ab62ee37320074df401c3986b56f3ea6cbfa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130400"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI)
[封印された](../windows/sealed-cpp-component-extensions.md)、[抽象](../windows/abstract-cpp-component-extensions.md)、および[オーバーライド](../windows/override-cpp-component-extensions.md)は使用しないでコンパイルで使用可能な **/ZW**または[/clr](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
> [!NOTE]
>  ISO c 11 標準の言語が、[オーバーライド](../cpp/override-specifier.md)識別子と[最終](../cpp/final-specifier.md)識別子、および両方が Visual Studio の使用でサポートされている`final`の代わりに`sealed`ものではコードで(ネイティブのみ) としてコンパイルします。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例に示しますを`sealed`はネイティブ コンパイルで有効です。  
  
### <a name="code"></a>コード  
  
```cpp  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例を`override`はネイティブ コンパイルで有効です。  
  
### <a name="code"></a>コード  
  
```cpp  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例`abstract`はネイティブ コンパイルで有効です。  
  
### <a name="code"></a>コード  
  
```cpp  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)