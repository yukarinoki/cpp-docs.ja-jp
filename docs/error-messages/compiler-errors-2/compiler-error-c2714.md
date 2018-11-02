---
title: コンパイラ エラー C2714
ms.date: 11/04/2016
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: feba363a7cd15d92bf850e8cba457ff310d15490
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556365"
---
# <a name="compiler-error-c2714"></a>コンパイラ エラー C2714

__alignof(void) は許可されていません

無効な値は、演算子に渡されました。

参照してください[_ _alignof 演算子](../../cpp/alignof-operator.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C2714 が生成されます。

```
// C2714.cpp
int main() {
   return __alignof(void);   // C2714
   return __alignof(char);   // OK
}
```