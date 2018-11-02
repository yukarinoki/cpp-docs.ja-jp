---
title: コンパイラ エラー C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: b52797b945b1a652506b4a85171e60a91544bbf0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546482"
---
# <a name="compiler-error-c2190"></a>コンパイラ エラー C2190

2 つ目を超える最初のパラメーター リスト

C の関数は、パラメーター一覧を短くしてもう一度で宣言されました。 C では、オーバー ロードされた関数はサポートされません。

次の例では、C2190 が生成されます。

```
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```