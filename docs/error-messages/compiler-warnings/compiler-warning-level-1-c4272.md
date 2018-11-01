---
title: コンパイラの警告 (レベル 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 26e136aa395729d520f4a71a06b6dc212cf21f8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479991"
---
# <a name="compiler-warning-level-1-c4272"></a>コンパイラの警告 (レベル 1) C4272

'function': _declspec; がマークされています。関数をインポートするときに、ネイティブの呼び出し規約を指定する必要があります。

マークされた関数をエクスポートするとエラーには、 [_ _clrcall](../../cpp/clrcall.md)でマークされた関数をインポートしようとした場合、この警告を発行呼び出し規約、およびコンパイラ`__clrcall`します。

次の例では、C4272 が生成されます。

```
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```