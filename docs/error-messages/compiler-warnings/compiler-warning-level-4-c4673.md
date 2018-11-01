---
title: コンパイラの警告 (レベル 4) C4673
ms.date: 11/04/2016
f1_keywords:
- C4673
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
ms.openlocfilehash: ceaa5cd647dfb527713613b9ce3b5cd81a780fd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657731"
---
# <a name="compiler-warning-level-4-c4673"></a>コンパイラの警告 (レベル 4) C4673

'identifier' に、次の種類をスローすることは考慮されません catch サイト

Throw オブジェクトで処理することはできません、**キャッチ**ブロックします。 各型を処理することはできませんが、この警告が含まれる行の直後のエラー出力に表示されます。 ハンドルされていない各種では、独自の警告があります。 詳細については、各型の警告を確認します。

次の例では、C4673 が生成されます。

```
// C4673.cpp
// compile with: /EHsc /W4
class Base {
private:
   char * m_chr;
public:
   Base() {
      m_chr = 0;
   }

   ~Base() {
      if(m_chr)
         delete m_chr;
   }
};

class Derv : private Base {
public:
   Derv() {}
   ~Derv() {}
};

int main() {
   try {
      Derv D1;
      // delete previous line, uncomment the next line to resolve
      // Base D1;
      throw D1;   // C4673
   }

   catch(...) {}
}
```