---
title: コンパイラの警告 (レベル 3) C4334 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7bb16ea38b2c2112c12c561398341a7d1adbfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044016"
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