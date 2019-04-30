---
title: コンパイラ エラー C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 1482efa8b018914a4ebc509464622726ae9ebb20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383010"
---
# <a name="compiler-error-c2838"></a>コンパイラ エラー C2838

'member' : illegal qualified name in member declaration

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