---
title: コンパイラ エラー C2383 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c529c22636f112291fa53b852899cad78dac589
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113228"
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