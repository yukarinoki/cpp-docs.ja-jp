---
title: コンパイラ エラー C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 06d4c19208bd242169e1cd07a71e8a568f46f7b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466093"
---
# <a name="compiler-error-c2383"></a>コンパイラ エラー C2383

'*シンボル*': 既定の引数はこのシンボルでは許可されていません

C++ コンパイラ、既定の引数を関数へのポインターにはできません。

このコードは、Visual Studio 2005 より前に、のバージョンの Visual C コンパイラによって受け入れられましたが、エラーになります。 Visual C のすべてのバージョンで動作するコードでは、関数へのポインター引数に既定値は割り当てないでください。

## <a name="example"></a>例

次の例では、C2383 を生成し、解決策を示しています。

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```