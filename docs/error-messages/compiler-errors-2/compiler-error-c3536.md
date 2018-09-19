---
title: コンパイラ エラー C3536 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3536
dev_langs:
- C++
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7585a75ebe9733c228756e92d8e5ae57699aca27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088580"
---
# <a name="compiler-error-c3536"></a>コンパイラ エラー C3536

'symbol': 初期化前に使用することはできません

初期化される前に、指定されたシンボルを使用できません。 実際には、変数はその変数自体を初期化するために使用できないことを意味します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. それ自体と変数を初期化できません。

## <a name="example"></a>例

次の例は、それ自体と各変数が初期化されて C3536 を生成します。

```
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)