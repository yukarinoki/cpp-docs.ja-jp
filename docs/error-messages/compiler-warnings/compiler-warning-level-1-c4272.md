---
title: コンパイラの警告 (レベル 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 747b9e60ad2b8b0036c6eac50d44c2d70277384f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163114"
---
# <a name="compiler-warning-level-1-c4272"></a>コンパイラの警告 (レベル 1) C4272

' function ': __declspec (dllimport) に設定されています。関数をインポートするときは、ネイティブ呼び出し規約を指定する必要があります。

[__Clrcall](../../cpp/clrcall.md)の呼び出し規約でマークされた関数をエクスポートするとエラーになります。 `__clrcall`とマークされた関数をインポートしようとすると、コンパイラはこの警告を発行します。

次の例では、C4272 が生成されます。

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
