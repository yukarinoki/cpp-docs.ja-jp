---
description: 詳細については、「コンパイラエラー C3457」を参照してください。
title: コンパイラ エラー C3457
ms.date: 11/04/2016
f1_keywords:
- C3457
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
ms.openlocfilehash: 42e30946c57da585ed1339e49b6081372b141a2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113598"
---
# <a name="compiler-error-c3457"></a>コンパイラ エラー C3457

'attribute': 属性は、名前が指定されていない引数をサポートしていません

CLR カスタム属性やコンパイラ属性とは異なり、ソースの注釈属性は名前付き引数のみをサポートします。

## <a name="example"></a>例

次の例では C3457 が生成されます。

```
#include "SourceAnnotations.h"
[vc_attributes::Post( 1 )] int f();   // C3457
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK
```
