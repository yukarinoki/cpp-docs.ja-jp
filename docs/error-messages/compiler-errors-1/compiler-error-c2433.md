---
description: 詳細については、「コンパイラエラー C2433」を参照してください。
title: コンパイラ エラー C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 67d7a0f34ef988c6d67a720a2af2d2fa493b2bf2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189952"
---
# <a name="compiler-error-c2433"></a>コンパイラ エラー C2433

' identifier ': ' modifier ' はデータ宣言で許可されていません

**`friend`**、 **`virtual`** 、および修飾子は、 **`inline`** データ宣言には使用できません。

## <a name="example"></a>例

次の例では、C2433 が生成されます。

```cpp
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```
