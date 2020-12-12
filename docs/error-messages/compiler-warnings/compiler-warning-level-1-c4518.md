---
description: '詳細情報: コンパイラの警告 (レベル 1) C4518'
title: コンパイラの警告 (レベル 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 1a04dbcdc62e6758e2b65c6b0ef5aa99a1823ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212299"
---
# <a name="compiler-warning-level-1-c4518"></a>コンパイラの警告 (レベル 1) C4518

' 指定子 ': ストレージクラスまたは型指定子が予期せずになりました。無効

次の例では、C4518 が生成されます。

```cpp
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```
