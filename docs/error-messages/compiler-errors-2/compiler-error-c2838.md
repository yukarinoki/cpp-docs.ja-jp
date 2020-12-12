---
description: 詳細については、「コンパイラエラー C2838」を参照してください。
title: コンパイラ エラー C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 70bc1fa038df33cfe63fccd7dc3db8983950b525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194398"
---
# <a name="compiler-error-c2838"></a>コンパイラ エラー C2838

' member ': メンバー宣言内の修飾名が無効です

クラス、構造体、または共用体は、別のクラス、構造体、または共用体のメンバーを再宣言するために、完全修飾名を使用します。

次の例では、C2838 が生成されます。

```cpp
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
