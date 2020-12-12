---
description: '詳細情報: コンパイラの警告 (レベル 3) C4334'
title: コンパイラの警告 (レベル 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 3c7a84efc3c98779c5b50dc1b3fb28e687f856eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344030"
---
# <a name="compiler-warning-level-3-c4334"></a>コンパイラの警告 (レベル 3) C4334

' operator ':32 ビットシフトの結果が64ビットに暗黙的に変換されました (64 ビットシフトが想定されていました)。

32ビットシフトの結果は、暗黙的に64ビットに変換され、64ビットシフトが意図されていることをコンパイラが推測します。  この警告を解決するには、64ビットシフトを使用するか、シフト結果を64ビットに明示的にキャストします。

## <a name="example"></a>例

次の例では、C4334 が生成されます。

```cpp
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```
