---
description: '詳細情報: コンパイラの警告 (レベル 1) C4804'
title: コンパイラの警告 (レベル 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 0e1260df9327e714c487159b7c0c8c1a1168bad9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334912"
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
