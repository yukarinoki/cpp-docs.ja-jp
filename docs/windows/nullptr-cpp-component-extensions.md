---
title: nullptr (C++ コンポーネント拡張) |Microsoft Docs
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
ms.openlocfilehash: 0596276589790ee6fae8e071e50b4d9b55dd8b85
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439615"
---
# <a name="nullptr--c-component-extensions"></a>nullptr (C++ コンポーネント拡張)

**Nullptr**キーワードを表す、 *null ポインター値*します。 Null ポインターの値を使用して、オブジェクト ハンドル、内部ポインター、またはネイティブ ポインターの型がオブジェクトをポイントがないことを示します。

使用**nullptr**マネージまたはネイティブ コードにします。 コンパイラは、マネージ コードとネイティブの null ポインターの値の適切なが別の手順を出力します。 このキーワードの ISO 標準 C++ 版の使用方法の詳細については、次を参照してください。 [nullptr](../cpp/nullptr.md)します。

**_ _Nullptr**キーワードは、Microsoft 固有キーワードと同じ意味のある**nullptr**、ネイティブ コードのみに適用されます。 使用する場合**nullptr**ネイティブ C/C++ コードを指定してコンパイルし、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、コンパイラが判断できないかどうか**nullptr**ネイティブことを示しますまたはnull ポインターの値を管理します。 オフにすると、コンパイラ、意図したものを作成するには使用**nullptr**管理対象の値を指定または **_ _nullptr**ネイティブ値を指定します。

**Nullptr**キーワードは等価**Nothing** Visual basic と**null** (C#)。

## <a name="usage"></a>使用法

**Nullptr**ハンドル、ネイティブ ポインター、または関数の引数を使用できる任意の場所キーワードを使用できます。

**Nullptr**キーワード型ではないでの使用はサポートされていません。

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr` (ただし`throw (Object^)nullptr;`は動作)

**Nullptr**キーワードは、次のポインター型の初期化で使用することができます。

- ネイティブ ポインター

- Windows ランタイム ハンドル

- 管理対象のハンドル

- 管理対象の内部ポインター

**Nullptr**キーワードを使用して参照を使用する前に、ポインターまたはハンドルの参照が null の場合をテストすることができます。

Null ポインターの値を使用して、エラー チェックの言語間での関数呼び出しを正しく解釈する必要があります。

0 以外を識別するハンドルを初期化することはできません。のみ**nullptr**ことができます。 定数 0 オブジェクト ハンドルの割り当てをボックス化された生成`Int32`へのキャストと`Object^`します。

## <a name="example"></a>例

次のコード例を示しますが、 **nullptr**場所、ネイティブ ポインター、ハンドルで使用できるキーワードまたは関数の引数を使用できます。 例を示すと、 **nullptr**キーワードを使用して、使用は、前に参照を確認することができます。

```cpp
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

コード例を次に示します**nullptr**とネイティブ ポインターに 0 を区別しないで使用できます。

```cpp
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

```Output
pMyClass == nullptr

pMyClass == 0

pMyClass == nullptr

pMyClass == 0
```

## <a name="example"></a>例

コード例を次に示します**nullptr**は任意の型を識別するハンドルまたは任意の型へのネイティブ ポインターとして解釈されます。 関数のオーバー ロードするためのさまざまな種類のハンドルが発生した場合、あいまいなエラーが生成されます。 **Nullptr**型に明示的にキャストする必要があります。

```cpp
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

次のコード例は、そのキャストを示しています。 **nullptr**が許可され、キャストの型を含むするポインターまたはハンドルを返します、 **nullptr**値。

```cpp
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

コード例を次に示します**nullptr**関数パラメーターとして使用できます。

```cpp
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

```Output
test
```

## <a name="example"></a>例

ハンドルが宣言されているし、明示的に初期化されない、既定値に初期化は、次のコード例に示します**nullptr**します。

```cpp
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

```Output
NULL
```

## <a name="example"></a>例

コード例を次に示します**nullptr**をコンパイルすると、ネイティブ ポインターに割り当てることができます`/clr`します。

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>要件

コンパイラ オプション: (いないために必要な; を含むすべてのコード生成オプションでサポートされている`/ZW`と`/clr`)

## <a name="see-also"></a>関連項目

[ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)