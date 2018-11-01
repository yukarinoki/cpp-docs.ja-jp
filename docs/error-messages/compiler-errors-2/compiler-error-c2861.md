---
title: コンパイラ エラー C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: e7cced7a9abd974d0cbcea69059459d6c15f9850
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514700"
---
# <a name="compiler-error-c2861"></a>コンパイラ エラー C2861

'関数の name': インターフェイスのメンバー関数を定義することはできません

メンバーを検出し、コンパイラは、interface キーワードが発生しましたか、インターフェイスとして構造体を推測が関数の定義。  インターフェイスは、メンバー関数の定義を含めることはできません。

## <a name="example"></a>例

次の例では、C2861 が生成されます。

```
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861

```