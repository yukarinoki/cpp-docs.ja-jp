---
title: nullptr (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33a276c383618531103a76b1f20c6ad478d57c10
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="nullptr--c-component-extensions"></a>nullptr (C++ コンポーネント拡張)
`nullptr`キーワードを表す、 *null ポインター値*です。 Null ポインター値を使用して、あるオブジェクトのハンドル、内部ポインター、またはネイティブ ポインター型を指していないオブジェクトを示します。  
  
 使用して`nullptr`マネージまたはネイティブ コードにします。 コンパイラは、適切なが異なるについては、マネージ コードとネイティブの null ポインターの値を出力します。 このキーワードの ISO 標準 C++ バージョンを使用する方法の詳細については、次を参照してください。 [nullptr](../cpp/nullptr.md)です。  
  
 `__nullptr`キーワードは Microsoft 固有キーワードと同じ意味のある`nullptr`がネイティブ コードのみに適用されます。 使用する場合`nullptr`ネイティブ C/C++ コードし、コンパイル時に、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、コンパイラが判断できないかどうか`nullptr`ネイティブまたはマネージの null ポインター値を示します。 目的は、オフにすると、コンパイラを使用します`nullptr`管理対象の値を指定するまたは`__nullptr`ネイティブ値を指定します。  
  
 `nullptr`キーワードは等価`Nothing`Visual Basic では、 `null` (C#)。  
  
## <a name="usage"></a>使用法  
 `nullptr`ハンドル、ネイティブ ポインター、または関数の引数を使用できる場所でキーワードを使用できます。  
  
 `nullptr`キーワード型ではないで使用することはできません。  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` (ただし`throw (Object^)nullptr;`は機能)  
  
 `nullptr`キーワードは、次のポインター型の初期化で使用することができます。  
  
-   ネイティブ ポインター  
  
-   Windows ランタイム ハンドル  
  
-   マネージ ハンドル  
  
-   管理対象の内部ポインター  
  
 `nullptr`キーワードは、参照を使用する前に、ポインターまたはハンドルの参照が null かどうかを使用できます。  
  
 エラーをチェックするための null ポインターの値を使用する言語の間での関数呼び出しを正しく解釈される必要があります。  
  
 ゼロ; へのハンドルを初期化することはできません。のみ`nullptr`使用できます。 定数 0 のオブジェクト ハンドルの割り当てをボックス化された生成`Int32`とへのキャスト`Object^`です。  
  
## <a name="example"></a>例  
 次のコード例では、ことを示します、`nullptr`キーワードを使用できるハンドル、ネイティブ ポインター、または関数の引数を使用することができます。 例では、ことを示しています、`nullptr`が使用する前に参照を確認するキーワードを使用できます。  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## <a name="example"></a>例  
 **例**  
  
 次のコード例に示しますを`nullptr`あり、ネイティブ ポインターに 0 を置き換えて使用できます。  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **出力**  
  
```Output  
pMyClass == nullptr  
  
pMyClass == 0  
  
pMyClass == nullptr  
  
pMyClass == 0  
```  
  
## <a name="example"></a>例  
 **例**  
  
 次のコード例に示しますを`nullptr`は任意の型へのハンドルまたは任意の型へのネイティブ ポインターとして解釈されます。 さまざまな種類にハンドルが関数のオーバー ロードが発生した場合、あいまいなエラーが生成されます。 `nullptr`型に明示的にキャストする必要があります。  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## <a name="example"></a>例  
 **例**  
  
 次のコード例は、そのキャストを示しています。`nullptr`が許可されを含むキャストの型へのポインターまたはハンドルを返します、`nullptr`値。  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## <a name="example"></a>例  
 **例**  
  
 次のコード例に示しますを`nullptr`関数のパラメーターとして使用できます。  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **出力**  
  
```Output  
test  
```  
  
## <a name="example"></a>例  
 **例**  
  
 次のコード例は、ハンドルが宣言されており、明示的に初期化されない、ときにある既定値に初期化を示しています。`nullptr`です。  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **出力**  
  
```Output  
NULL  
```  
  
## <a name="example"></a>例  
 **例**  
  
 次のコード例に示しますを`nullptr`をコンパイルすると、ネイティブ ポインターに割り当てることが **/clr**です。  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## <a name="requirements"></a>要件  
 コンパイラ オプション: (必要な; を含むすべてのコード生成オプションでサポートされていない **/ZW**と **/clr**)  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)