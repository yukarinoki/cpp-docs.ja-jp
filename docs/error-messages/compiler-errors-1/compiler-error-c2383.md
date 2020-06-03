---
title: コンパイラ エラー C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 2aa922ebeadb374a7eac73a0f452376472b00984
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206029"
---
# <a name="compiler-error-c2383"></a>コンパイラ エラー C2383

'*symbol*': 既定の引数はこのシンボルでは使用できません

コンパイラC++は、関数へのポインターに対して既定の引数を許可しません。

このコードは、Visual Studio 2005 C++より前のバージョンの Microsoft コンパイラによって受け入れられていましたが、エラーが発生しました。 すべてのバージョンのビジュアルC++で動作するコードの場合、ポインターから関数への引数に既定値を割り当てないでください。

## <a name="example"></a>例

次の例では、C2383 を生成し、考えられる解決方法を示します。

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
