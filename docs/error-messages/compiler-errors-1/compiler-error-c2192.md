---
description: 詳細については、「コンパイラエラー C2192」を参照してください。
title: コンパイラ エラー C2192
ms.date: 11/04/2016
f1_keywords:
- C2192
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
ms.openlocfilehash: 02b1b5ace60d2b9a288cf933a43c5603b734eac7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337681"
---
# <a name="compiler-error-c2192"></a>コンパイラ エラー C2192

パラメーター ' number ' の宣言が異なります

C 関数は、別のパラメーターリストを使用して2回目に宣言されました。 C は、オーバーロードされた関数をサポートしていません。

次の例では、C2192 が生成されます。

```c
// C2192.c
// compile with: /Za /c
void func( float, int );
void func( int, float );   // C2192, different parameter list
void func2( int, float );   // OK
```
