---
title: コンパイラの警告 (レベル 3) C4640
ms.date: 11/04/2016
f1_keywords:
- C4640
helpviewer_keywords:
- C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
ms.openlocfilehash: ccfb82852325437a739d7a8f8a5c5b06ce5f9714
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401684"
---
# <a name="compiler-warning-level-3-c4640"></a>コンパイラの警告 (レベル 3) C4640

'instance': ローカル スタティック オブジェクトの構築がスレッド セーフではありません

オブジェクトの静的インスタンスは、スレッド セーフではありません。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、(c4640) が生成されます。

```
// C4640.cpp
// compile with: /W3
#pragma warning(default:4640)

class X {
public:
   X() {
   }
};

void f() {
   static X aX;   // C4640
}

int main() {
   f();
}
```