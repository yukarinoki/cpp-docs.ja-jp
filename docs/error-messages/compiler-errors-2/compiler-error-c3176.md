---
title: コンパイラ エラー C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: 8c92a49499a18c12807f97cb97b24cc3beaf700b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474426"
---
# <a name="compiler-error-c3176"></a>コンパイラ エラー C3176

'type': ローカルの値の型を宣言することはできません

クラスは、グローバル スコープで値の型としてのみ宣言できます。

## <a name="example"></a>例

次の例では、C3176 が生成されます。

```
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```