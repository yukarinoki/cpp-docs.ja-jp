---
title: '方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: 114d1bd3677537029f336f4de3675015f1725214
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612863"
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)

**Interior_ptr**値型で使用できます。

> [!IMPORTANT]
> この言語機能がサポートされている、`/clr`コンパイラ オプションがなく、`/ZW`コンパイラ オプション。

## <a name="example"></a>例

### <a name="description"></a>説明

次の C +/cli CLI のサンプルを使用する方法を示しています、 **interior_ptr**が値型。

### <a name="code"></a>コード

```cpp
// interior_ptr_value_types.cpp
// compile with: /clr
value struct V {
   V(int i) : data(i){}
   int data;
};

int main() {
   V v(1);
   System::Console::WriteLine(v.data);

   // pointing to a value type
   interior_ptr<V> pv = &v;
   pv->data = 2;

   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);

   // pointing into a value type
   interior_ptr<int> pi = &v.data;
   *pi = 3;
   System::Console::WriteLine(*pi);
   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);
}
```

```Output
1
2
2
3
3
3
```

## <a name="example"></a>例

### <a name="description"></a>説明

値の型で、**この**interior_ptr にポインターが評価されます。

値型の非静的メンバー関数の本体で`V`、**この**型の式は、`interior_ptr<V>`値を持つ関数を呼び出すオブジェクトのアドレスになります。

### <a name="code"></a>コード

```cpp
// interior_ptr_value_types_this.cpp
// compile with: /clr /LD
value struct V {
   int data;
   void f() {
      interior_ptr<V> pv1 = this;
      // V* pv2 = this;   error
   }
};
```

## <a name="example"></a>例

### <a name="description"></a>説明

次の例では、静的メンバーとアドレス演算子を使用する方法を示します。

Visual C 型の静的メンバーのアドレスは、ネイティブ ポインターを生成します。  静的な値型のメンバーのアドレスは、値型のメンバーはランタイム ヒープに割り当てられているし、ガベージ コレクターを移動するためのマネージ ポインターです。

### <a name="code"></a>コード

```cpp
// interior_ptr_value_static.cpp
// compile with: /clr
using namespace System;
value struct V { int i; };

ref struct G {
   static V v = {22};
   static int i = 23;
   static String^ pS = "hello";
};

int main() {
   interior_ptr<int> p1 = &G::v.i;
   Console::WriteLine(*p1);

   interior_ptr<int> p2 = &G::i;
   Console::WriteLine(*p2);

   interior_ptr<String^> p3 = &G::pS;
   Console::WriteLine(*p3);
}
```

```Output
22
23
hello
```

## <a name="see-also"></a>関連項目

[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)