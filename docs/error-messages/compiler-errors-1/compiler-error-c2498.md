---
description: 詳細については、「コンパイラエラー C2498」を参照してください。
title: コンパイラ エラー C2498
ms.date: 11/04/2016
f1_keywords:
- C2498
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
ms.openlocfilehash: e7cbb811cdaeea703d0f1da1c0f2012ebe8210fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335100"
---
# <a name="compiler-error-c2498"></a>コンパイラ エラー C2498

' function ': ' novtable ' は、クラス宣言または定義にのみ適用できます

このエラーは、関数でを使用した場合に発生する可能性があり `__declspec(novtable)` ます。

## <a name="example"></a>例

次の例では、C2498 が生成されます。

```cpp
// C2498.cpp
// compile with: /c
void __declspec(novtable) f() {}   // C2498
class __declspec(novtable) A {};   // OK
```
