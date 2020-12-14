---
description: 詳細については、「コンパイラエラー C2381」を参照してください。
title: コンパイラ エラー C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: ccaed8e5fc637ffb7e5cd2a33a00ddb5cf7c102b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282180"
---
# <a name="compiler-error-c2381"></a>コンパイラ エラー C2381

' function ': 再定義します。__declspec (noreturn) が異なる

関数が宣言されて定義されましたが、定義では [noreturn](../../cpp/noreturn.md)修飾子が使用されてい **`__declspec`** ます。 を使用すると、 `noreturn` 関数の再定義が構成されます。宣言と定義は、の使用に同意する必要があり `noreturn` ます。

次の例では、C2381 が生成されます。

```cpp
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```
