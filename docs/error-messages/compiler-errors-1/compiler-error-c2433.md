---
title: コンパイラ エラー C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: f8cd8d5c165b796dff5260e84a505356f2a74941
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216220"
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
