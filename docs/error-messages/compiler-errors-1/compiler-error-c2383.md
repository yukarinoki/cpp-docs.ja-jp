---
description: 詳細については、「コンパイラエラー C2383」を参照してください。
title: コンパイラ エラー C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 862346d7f2bfe92a5d2182a7fe53f260b357ad0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185935"
---
# <a name="compiler-error-c2383"></a>コンパイラ エラー C2383

'*symbol*': 既定の引数はこのシンボルでは使用できません

C++ コンパイラでは、関数へのポインターで既定の引数を使用することはできません。

このコードは、Visual Studio 2005 より前のバージョンでは、Microsoft C++ コンパイラによって受け入れられましたが、ここではエラーが発生します。 Visual C++ のすべてのバージョンで動作するコードの場合、ポインターから関数への引数に既定値を割り当てないでください。

## <a name="example"></a>例

次の例では、C2383 を生成し、考えられる解決方法を示します。

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
