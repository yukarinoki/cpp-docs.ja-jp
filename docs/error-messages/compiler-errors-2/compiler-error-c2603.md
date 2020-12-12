---
description: 詳細については、「コンパイラエラー C2603」を参照してください。
title: コンパイラエラー C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: e28ea581c4c1417972cddc0ce558bd518acb8889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208789"
---
# <a name="compiler-error-c2603"></a>コンパイラエラー C2603

> '*function*': 関数内のコンストラクターまたはデストラクターを含むブロックスコープの静的オブジェクトが多すぎます。

Visual Studio 2015 より前のバージョンの Microsoft C++ コンパイラ、または [/zc: threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) コンパイラオプションが指定されている場合、外部から参照可能なインライン関数で保持できる静的オブジェクトの数には、31の制限があります。

この問題を解決するには、より新しいバージョンの Microsoft C++ コンパイラツールセットを採用するか、可能であれば/Zc: threadSafeInit-コンパイラオプションを削除することをお勧めします。 これが不可能な場合は、静的オブジェクトを組み合わせることを検討してください。 オブジェクトが同じ型である場合は、その型の単一の静的配列を使用することを検討し、必要に応じて個々のメンバーを参照します。

## <a name="example"></a>例

次のコードは、C2603 を生成し、その修正方法の1つを示しています。

```cpp
// C2603.cpp
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };
extern inline void f1() {
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;
    static C C32;   // C2603 Comment this line out to avoid error
}
```
