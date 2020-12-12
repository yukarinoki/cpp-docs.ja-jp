---
description: 詳細については、「コンパイラエラー C2714」を参照してください。
title: コンパイラエラー C2714
ms.date: 07/22/2020
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: 7bea0fc27de49f5767b8b250254f255964423cdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320832"
---
# <a name="compiler-error-c2714"></a>コンパイラエラー C2714

> `alignof(void)` 使用できません

演算子に無効な値が渡されました。

## <a name="remarks"></a>解説

詳細については、「 [ `alignof` 演算子](../../cpp/alignof-operator.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2714 が生成されます。

```cpp
// C2714.cpp
int main() {
   return alignof(void);   // C2714
   return alignof(char);   // OK
}
```
