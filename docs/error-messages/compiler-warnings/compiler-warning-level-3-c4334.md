---
title: コンパイラの警告 (レベル 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 55512bf28c8c20512d0d245810d3e5c1fec36939
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402035"
---
# <a name="compiler-warning-level-3-c4334"></a>コンパイラの警告 (レベル 3) C4334

'operator': 32 ビット シフトの結果が暗黙的に変換する 64 ビット (64 ビット シフトのためのものでしたか?)

32 ビット シフトの結果は、64 ビットと 64 ビット シフトを意図するコンパイラ %sort% に暗黙的に変換されました。  この警告を解決するには、64 ビット シフトを使用するかを 64 ビット シフトの結果を明示的にキャストします。

## <a name="example"></a>例

次の例では、C4334 が生成されます。

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```