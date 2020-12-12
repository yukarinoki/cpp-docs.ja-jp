---
description: 詳細については、「コンパイラエラー C2971」を参照してください。
title: コンパイラ エラー C2971
ms.date: 11/04/2016
f1_keywords:
- C2971
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
ms.openlocfilehash: 51cecf7fcf80b93231763bb183b870760820ca7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210388"
---
# <a name="compiler-error-c2971"></a>コンパイラ エラー C2971

' class ': テンプレートパラメーター ' param ': ' arg ': ローカル変数を非型引数として使用することはできません

ローカル変数の名前またはアドレスをテンプレート引数として使用することはできません。

次の例では、C2971 が生成されます。

```cpp
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```
