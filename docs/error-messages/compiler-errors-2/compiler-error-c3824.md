---
description: 詳細については、「コンパイラエラー C3824」を参照してください。
title: コンパイラ エラー C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: 5560ee8c845c57ae14de11b503ebc724dbcbb0dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249361"
---
# <a name="compiler-error-c3824"></a>コンパイラ エラー C3824

' member ': この型はこのコンテキストには記述できません (関数パラメーター、戻り値の型、または静的メンバー)

ピン留めポインターを関数パラメーター、戻り値の型、または宣言することはできません **`static`** 。

## <a name="example"></a>例

次の例では、C3824 が生成されます。

```cpp
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
