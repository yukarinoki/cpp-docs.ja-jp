---
title: コンパイラの警告 (レベル 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: aa2cdf0103a1ccc607f2e4a55e1d8f85bb8cc45d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233224"
---
# <a name="compiler-warning-level-1-c4804"></a>コンパイラの警告 (レベル 1) C4804

' operation ': 操作中に型 ' bool ' を使用することは安全ではありません

この警告は、 **`bool`** 予期しない方法で変数または値を使用した場合に発生します。 たとえば、負の単項演算子 ( **-** ) や補数演算子 () などの演算子を使用すると、C4804 が生成され `~` ます。 コンパイラは、式を評価します。

## <a name="example"></a>例

次の例では、C4804 が生成されます。

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```
