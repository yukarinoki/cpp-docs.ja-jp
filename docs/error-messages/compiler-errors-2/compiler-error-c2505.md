---
title: コンパイラ エラー C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: bf5ffb9b6bad3db1d264941a6aefa391be521c98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165041"
---
# <a name="compiler-error-c2505"></a>コンパイラ エラー C2505

'symbol': '__declspec(modifer)' は宣言またはグローバル オブジェクトまたは静的データ メンバーの定義にのみ適用できます

A`__declspec`グローバル スコープでのみ使用するように設計された修飾子は関数で使用されました。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。

次の例では、C2505 が生成されます。

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```