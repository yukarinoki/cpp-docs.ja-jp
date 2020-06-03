---
title: コンパイラの警告 (レベル 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: a8eae1ddeb875d267b82c67e989cb41e8c9b2afb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185452"
---
# <a name="compiler-warning-level-3-c4686"></a>コンパイラの警告 (レベル 3) C4686

> '*ユーザー定義型*': 動作が変更される可能性があります。 UDT の戻り値の呼び出し規約が変更されています。

## <a name="remarks"></a>解説

クラステンプレートの特殊化は、戻り値の型で使用される前に定義されていません。 クラスをインスタンス化するすべてのものが C4686 を解決します。インスタンスの宣言またはメンバーへのアクセス (C\<int >:: すべて) は、オプションでもあります。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

代わりに、次のようにしてください。

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```
