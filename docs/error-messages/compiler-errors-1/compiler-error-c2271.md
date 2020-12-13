---
description: 詳細については、「コンパイラエラー C2271」を参照してください。
title: コンパイラ エラー C2271
ms.date: 11/04/2016
f1_keywords:
- C2271
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
ms.openlocfilehash: 750af0551aadc274ea2c90f265fe9df9e0e9ab6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336278"
---
# <a name="compiler-error-c2271"></a>コンパイラ エラー C2271

' operator ': new/delete に仮引数リスト修飾子を含めることはできません

演算子 ( **`new`** または **`delete`** ) は、メモリモデル指定子を使用して宣言されています。

次の例では、C2271 が生成されます。

```cpp
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```
