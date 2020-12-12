---
description: '詳細情報: コンパイラの警告 (レベル 1) C4272'
title: コンパイラの警告 (レベル 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: a44e3a4121c1d01b15af47b0b4eefb1f982423bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266118"
---
# <a name="compiler-warning-level-1-c4272"></a>コンパイラの警告 (レベル 1) C4272

' function ': __declspec (dllimport) に設定されています。関数をインポートするときは、ネイティブ呼び出し規約を指定する必要があります。

[__Clrcall](../../cpp/clrcall.md)の呼び出し規約でマークされた関数をエクスポートするとエラーになります。とマークされた関数をインポートしようとすると、コンパイラはこの警告を発行し `__clrcall` ます。

次の例では、C4272 が生成されます。

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
