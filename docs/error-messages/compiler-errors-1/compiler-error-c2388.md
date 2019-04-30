---
title: コンパイラ エラー C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 62afcb1fafc19d3d61a86f2fbc10cb99e095afc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393663"
---
# <a name="compiler-error-c2388"></a>コンパイラ エラー C2388

'symbol': シンボルは、両方 __declspec(appdomain) で宣言することはできませんと\__declspec(process)

 `appdomain` および `process` `__declspec` 修飾子は、同じシンボルでは使用できません。 変数のストレージは、プロセスごとまたはアプリケーション ドメインごとに存在します。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。

次の例では C2388 が生成されます。

```
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```