---
description: 詳細については、「コンパイラエラー C2198」を参照してください。
title: コンパイラ エラー C2198
ms.date: 11/04/2016
f1_keywords:
- C2198
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
ms.openlocfilehash: 60c07bdaa422a3844bf17355fd88e7924ce05dc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170036"
---
# <a name="compiler-error-c2198"></a>コンパイラ エラー C2198

'function' : 呼び出しに対する引数が少なすぎます。

コンパイラで検出された関数を呼び出すためのパラメーターが少なすぎるか、または関数宣言が正しくありません。

次の例では C2198 が生成されます。

```c
// C2198.c
// compile with: /c
void func( int, int );
int main() {
   func( 1 );   // C2198 only one actual parameter
   func( 1, 1 );   // OK
}
```
