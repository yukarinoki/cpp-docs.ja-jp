---
title: コンパイラ エラー C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: eabed85c61eaaa43b0106e0011f0357ece2e1ae1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221173"
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
