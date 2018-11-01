---
title: コンパイラ エラー C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 1482efa8b018914a4ebc509464622726ae9ebb20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560385"
---
# <a name="compiler-error-c2838"></a>コンパイラ エラー C2838

'member': メンバー宣言での無効な修飾名

クラス、構造体または共用体は、別のクラス、構造体、または共用体のメンバーを再宣言するのに完全修飾名を使用します。

次の例では、C2838 が生成されます。

```
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```