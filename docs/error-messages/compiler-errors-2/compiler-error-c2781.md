---
title: コンパイラ エラー C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: be665d86cf230c364f522fd1ad74cd5a124ac9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382971"
---
# <a name="compiler-error-c2781"></a>コンパイラ エラー C2781

'declaration': 以上が必要です value1 引数 - value2 の提供

変数パラメーター リストを持つ関数テンプレートは、引数が少なすぎます。

次の例では、C2781 が生成されます。

```
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```