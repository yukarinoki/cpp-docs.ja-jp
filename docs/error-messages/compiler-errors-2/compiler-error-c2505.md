---
description: 詳細については、「コンパイラエラー C2505」を参照してください。
title: コンパイラ エラー C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: 46054594731b8e39f4cb4b13e71559fcdbd2a55d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213014"
---
# <a name="compiler-error-c2505"></a>コンパイラ エラー C2505

' symbol ': ' __declspec (修飾子) ' は、グローバルオブジェクトまたは静的データメンバーの宣言または定義にのみ適用できます

**`__declspec`** グローバルスコープでのみ使用されるように設計された修飾子が関数で使用されました。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。

次の例では、C2505 が生成されます。

```cpp
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
