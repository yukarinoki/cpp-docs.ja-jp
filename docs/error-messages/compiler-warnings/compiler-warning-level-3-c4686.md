---
title: コンパイラの警告 (レベル 3) C4686
description: Microsoft C++ コンパイラの警告 C4686。
ms.date: 08/29/2020
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 6886ae7f413de630457b53e85b5cd75c4542ee19
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194498"
---
# <a name="compiler-warning-level-3-c4686"></a>コンパイラの警告 (レベル 3) C4686

> '*ユーザー定義型*': 動作が変更される可能性があります。 UDT の戻り値の呼び出し規約が変更されています。

## <a name="remarks"></a>注釈

クラステンプレートの特殊化は、戻り値の型で使用される前に定義されませんでした。 クラスをインスタンス化するすべてのものが C4686 を解決します。インスタンスの宣言またはメンバーへのアクセス (たとえば、 `C<int>::some_member` ) もオプションです。

既定では、この警告はオフに設定されています。 詳細については、「 [既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

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
