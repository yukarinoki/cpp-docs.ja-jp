---
title: コンパイラ エラー C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: d7c55ede285d027b1a65b33adbf6407df243f068
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635640"
---
# <a name="compiler-error-c3824"></a>コンパイラ エラー C3824

'member': この型は、(関数のパラメーター、戻り値の型、または静的メンバー) は、このコンテキストで表示されることはできません

固定ポインターの型を返す、関数パラメーターにすることはできませんまたは宣言`static`します。

## <a name="example"></a>例

次の例では、C3824 が生成されます。

```
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
