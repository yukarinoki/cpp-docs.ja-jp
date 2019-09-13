---
title: コンパイラの警告 (レベル 4) C4673
ms.date: 11/04/2016
f1_keywords:
- C4673
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
ms.openlocfilehash: ceaa5cd647dfb527713613b9ce3b5cd81a780fd7
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741394"
---
# <a name="compiler-warning-level-4-c4673"></a>コンパイラの警告 (レベル 4) C4673

' identifier ' をスローすると、次の型はキャッチサイトでは考慮されません

Throw オブジェクトを**catch**ブロックで処理することはできません。 処理できない型は、この警告を含む行のすぐ後にあるエラー出力に一覧表示されます。 未処理の型ごとに独自の警告があります。 詳細については、特定の種類ごとの警告を参照してください。

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