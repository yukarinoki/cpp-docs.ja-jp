---
description: 詳細については、「コンパイラエラー C3176」を参照してください。
title: コンパイラエラー C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: 8dda09ccbe6faa80d77f43c38b2c94427956cc3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242042"
---
# <a name="compiler-error-c3176"></a>コンパイラエラー C3176

' type ': ローカル値の型を宣言することはできません

クラスは、グローバルスコープで値型としてのみ宣言できます。

## <a name="example"></a>例

次の例では、C3176 が生成されます。

```cpp
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```
