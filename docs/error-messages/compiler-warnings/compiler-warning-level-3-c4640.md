---
description: '詳細情報: コンパイラの警告 (レベル 3) (C4640)'
title: コンパイラの警告 (レベル 3) C4640
ms.date: 11/04/2016
f1_keywords:
- C4640
helpviewer_keywords:
- C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
ms.openlocfilehash: f0fc41256d11c54742a157236e09e36277902b5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338556"
---
# <a name="compiler-warning-level-3-c4640"></a>コンパイラの警告 (レベル 3) C4640

' instance ': ローカルの静的オブジェクトの構築はスレッドセーフではありません

オブジェクトの静的インスタンスは、スレッドセーフではありません。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、(C4640) が生成されます。

```cpp
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
