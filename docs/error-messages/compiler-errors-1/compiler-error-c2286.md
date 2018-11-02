---
title: コンパイラ エラー C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 7d3b8297c5f5da29b99abe78999396e8c44df0fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667507"
---
# <a name="compiler-error-c2286"></a>コンパイラ エラー C2286

'identifier' の形式のメンバーへのポインターが既に宣言は無視されます '継承' に設定されています。

クラスには、2 つの異なるメンバーへのポインター表現が存在します。

詳細については、次を参照してください。[継承キーワード](../../cpp/inheritance-keywords.md)します。

## <a name="example"></a>例

次の例では C2286 が生成されます。

```
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```