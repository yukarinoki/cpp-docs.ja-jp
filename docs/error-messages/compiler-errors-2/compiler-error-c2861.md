---
title: コンパイラ エラー C2861 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94210350e0483b46eb86579b837501a5291bda4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037256"
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