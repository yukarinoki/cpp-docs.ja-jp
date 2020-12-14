---
description: 詳細については、「リンカツール Error LNK2020」を参照してください。
title: リンカ ツール エラー LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 61e999b2f451359e3a806bc2da5f2beb431e6fab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275855"
---
# <a name="linker-tools-error-lnk2020"></a>リンカ ツール エラー LNK2020

未解決のトークン ' token '

未定義の外部エラーに似ていますが、メタデータを介して参照が使用されている点が異なります。 メタデータでは、すべての関数とデータを定義する必要があります。

解決するには、以下を行います。

- 不足している関数またはデータを定義します。

- 不足している関数またはデータが既に定義されているオブジェクトファイルまたはライブラリを含めます。

## <a name="examples"></a>例

次の例では、LNK2020 が生成されます。

```cpp
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

マネージテンプレート型の変数を作成しても、型をインスタンス化しない場合も、LNK2020 が発生します。

次の例では、LNK2020 が生成されます。

```cpp
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```
