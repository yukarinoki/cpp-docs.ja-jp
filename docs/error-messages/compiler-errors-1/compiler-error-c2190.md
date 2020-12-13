---
description: 詳細については、「コンパイラエラー C2190」を参照してください。
title: コンパイラ エラー C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: aeee732ff819746afa3bc572d4c090a694707afd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337690"
---
# <a name="compiler-error-c2190"></a>コンパイラ エラー C2190

最初のパラメーターリストが秒より長くなっています

C 関数は、より短いパラメーターリストを使用して2回目に宣言されました。 C は、オーバーロードされた関数をサポートしていません。

次の例では、C2190 が生成されます。

```c
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```
