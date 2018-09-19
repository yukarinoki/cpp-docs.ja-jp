---
title: コンパイラの警告 (レベル 3) C4800 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5a19c27731192a5fe2930aec3e78fb66d790484
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090908"
---
# <a name="compiler-warning-level-3-c4800"></a>コンパイラの警告 (レベル 3) C4800

> '*型*': 値を強制的にブール値は 'true' または 'false' (パフォーマンスの警告)

値ができない場合、この警告は生成`bool`が割り当てられているか、型に強制変換`bool`します。 通常、このメッセージは割り当てることで発生`int`変数`bool`変数を`int`変数には値のみが含まれています**true**と**false**、可能性があります型として再宣言`bool`します。 型を使用する式を書き直すことができない場合`bool`、追加することができますし、"`!=0`"式の型を式に示す`bool`します。 式の型にキャスト`bool`デザインでは、警告は無効にします。

この警告は、Visual Studio 2017 では生成されなくなりました。

## <a name="example"></a>例

次の例では、C4800 を生成し、その修正方法を示しています。

```cpp
// C4800.cpp
// compile with: /W3
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```