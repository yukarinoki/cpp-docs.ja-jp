---
description: 詳細については、「コンパイラエラー C2480」を参照してください。
title: コンパイラ エラー C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 0c7f73b7e1aa205d38577602b93907309935b216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316545"
---
# <a name="compiler-error-c2480"></a>コンパイラ エラー C2480

' identifier ': ' thread ' は静的なデータ項目に対してのみ有効です

`thread`自動変数、非静的データメンバー、関数パラメーター、または関数の宣言または定義で属性を使用することはできません。

`thread`グローバル変数、静的データメンバー、およびローカルの静的変数に対してのみ属性を使用します。

次の例では、C2480 が生成されます。

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
