---
description: 詳細については、「コンパイラエラー C3465」を参照してください。
title: コンパイラ エラー C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: ab5d55b5e21241eb2bbab00524f3c81baaace88f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113455"
---
# <a name="compiler-error-c3465"></a>コンパイラ エラー C3465

型 'type' を使用するには、アセンブリ 'assembly' を参照しなければなりません

クライアント アプリケーションで型の転送が機能するのは、クライアントを再コンパイルするまでの間です。 再コンパイルする場合は、クライアント アプリケーションで使用される型の定義を含む各アセンブリの参照が必要です。

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)」を参照してください。

## <a name="examples"></a>例

次の例では、型の新しい場所を含むアセンブリを作成します。

```cpp
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

次の例は型定義を含んでいたアセンブリを作成しますが、今回は型の転送構文が含まれています。

```cpp
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

次の例では C3465 が生成されます。

```cpp
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```
