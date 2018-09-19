---
title: コンパイラ エラー C2781 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2781
dev_langs:
- C++
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3662a1be167f6a443606139ff49daebc5c923eec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095483"
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