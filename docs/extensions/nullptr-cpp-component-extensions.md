---
title: nullptr (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 7e9cf88fdc0444f736f1cfac0d06dfc675a162cc
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008353"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr (C++/CLI および C++/CX)

キーワードは、 **`nullptr`** *null ポインター値*を表します。 Null ポインター値は、オブジェクト ハンドル、内部ポインター、またはネイティブ ポインターの型がオブジェクトを指していないことを示すために使用します。

**`nullptr`** マネージコードまたはネイティブコードと共にを使用します。 コンパイラからは、マネージドおよびネイティブの Null ポインター値に適した異なる命令が発行されます。 このキーワードの ISO 標準の C++ バージョンの使用については、「[nullptr](../cpp/nullptr.md)」を参照してください。

**__Nullptr**キーワードは、と同じ意味を持つ Microsoft 固有のキーワードです **`nullptr`** が、ネイティブコードにのみ適用されます。 を **`nullptr`** ネイティブ c/c + + コードと共に使用し、 [/clr](../build/reference/clr-common-language-runtime-compilation.md) コンパイラオプションを指定してコンパイルする場合、が **`nullptr`** ネイティブまたはマネージの null ポインター値を示すかどうかをコンパイラで判断できません。 コンパイラに対して意図を明確にするために、を使用して **`nullptr`** マネージ値を指定するか、 **__nullptr** ネイティブ値を指定します。

**`nullptr`** キーワードは、C# で**Nothing**は Visual Basic と**null**に相当します。

## <a name="usage"></a>使用法

キーワードは、 **`nullptr`** ハンドル、ネイティブポインター、または関数引数を使用できる任意の場所で使用できます。

**`nullptr`** キーワードが型ではなく、での使用がサポートされていません。

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr` (ただし `throw (Object^)nullptr;` は機能します)

キーワードは、 **`nullptr`** 次のポインター型を初期化するときに使用できます。

- ネイティブ ポインター

- Windows ランタイム ハンドル

- マネージド ハンドル

- マネージド内部ポインター

キーワードを使用して、 **`nullptr`** 参照が使用される前にポインターまたはハンドル参照が null であるかどうかをテストできます。

エラー チェックに Null ポインター値を使用する言語間の関数呼び出しは、正しく解釈されます。

ハンドルをゼロに初期化することはできません。のみ **`nullptr`** 使用できます。 オブジェクト ハンドルに定数 0 を割り当てると、ボックス化された `Int32` と `Object^` へのキャストが生成されます。

## <a name="example-nullptr-keyword"></a>例: `nullptr` キーワード

次のコード例は、 **`nullptr`** ハンドル、ネイティブポインター、または関数の引数を使用できる場所であれば、キーワードを使用できることを示しています。 この例では、キーワードを使用 **`nullptr`** して、参照を使用する前に確認できることを示しています。

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

## <a name="example-use-nullptr-and-zero-interchangeably"></a>例: 使用 `nullptr` とゼロの区別

次のコード例は、 **`nullptr`** と0をネイティブポインターで同義に使用できることを示しています。

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

## <a name="example-interpret-nullptr-as-a-handle"></a>例: `nullptr` ハンドルとして解釈する

次のコード例は、が任意の型への **`nullptr`** ハンドル、または任意の型へのネイティブポインターとして解釈されることを示しています。 異なる型へのハンドルを使用した関数のオーバーロードの場合、あいまいさのエラーが発生します。 は、 **`nullptr`** 型に明示的にキャストする必要があります。

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

## <a name="example-cast-nullptr"></a>例: Cast `nullptr`

キャストが許可され、 **`nullptr`** 値を格納するキャスト型へのポインターまたはハンドルを返すコード例を次に示します **`nullptr`** 。

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

## <a name="example-pass-nullptr-as-a-function-parameter"></a>例: `nullptr` 関数パラメーターとして渡す

次のコード例は、を **`nullptr`** 関数パラメーターとして使用できることを示しています。

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

## <a name="example-default-initialization"></a>例: 既定の初期化

次のコード例では、ハンドルが宣言されており、明示的に初期化されていない場合、既定値はに初期化されることを示してい **`nullptr`** ます。

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

## <a name="example-assign-nullptr-to-a-native-pointer"></a>例: `nullptr` ネイティブポインターに割り当てる

次のコード例は、を **`nullptr`** 使用してコンパイルするときに、をネイティブポインターに割り当てることができることを示して `/clr` います。

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>必要条件

コンパイラオプション: (必須ではありません。、、など、すべてのコード生成オプションでサポートされています `/ZW` `/clr` )

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)
