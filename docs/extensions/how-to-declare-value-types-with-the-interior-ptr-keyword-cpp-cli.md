---
description: '詳細については、「方法: interior_ptr キーワードを使用して値型を宣言する (C++/CLI)」を参照してください。'
title: '方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: b8d5c554f212a9536b0ad063d67e044c08194015
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119175"
---
# <a name="how-to-declare-value-types-with-the-interior_ptr-keyword-ccli"></a>方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)

値型で **Interior_ptr** を使用できます。

> [!IMPORTANT]
> この言語機能は、`/clr` コンパイラ オプションではサポートされていますが、`/ZW` コンパイラ オプションではサポートされていません。

## <a name="example-interior_ptr-with-value-type"></a>例: 値型の interior_ptr

### <a name="description"></a>説明

次の C++/CLI の例では、値型で **interior_ptr** を使用する方法を示します。

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

## <a name="example-this-pointer"></a>例: this ポインター

### <a name="description"></a>説明

値型では、 **`this`** ポインターは interior_ptr に評価されます。

値型の静的でないメンバー関数の本体で `V` **`this`** は、は、 `interior_ptr<V>` 関数が呼び出されるオブジェクトのアドレスを値とする型の式です。

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

## <a name="example-address-of-operator"></a>例: アドレス演算子

### <a name="description"></a>説明

次の例では、静的メンバーを持つ address-of 演算子を使用する方法を示します。

静的な Visual C++ 型のメンバーのアドレスは、ネイティブ ポインターを生成します。  静的な値型のメンバーのアドレスは、値型のメンバーがランタイム ヒープに割り当てられ、ガベージ コレクターによって移動される可能性があるため、マネージ ポインターになります。

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

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)
