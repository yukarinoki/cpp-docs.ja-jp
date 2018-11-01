---
title: コンパイラ エラー C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: 051468ea861190dd3f6a28dc272f1bab155145af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558900"
---
# <a name="compiler-error-c2364"></a>コンパイラ エラー C2364

'type': 無効な型のカスタム属性

カスタム属性の名前付き引数は、コンパイル時の定数に限定されます。 たとえば、整数型 (int、char など) system::type ^、および system::object ^ です。

## <a name="example"></a>例

次の例では、C2364 が生成されます。

```
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```