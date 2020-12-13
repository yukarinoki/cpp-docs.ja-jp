---
description: 詳細については、「コンパイラエラー C2262」を参照してください。
title: コンパイラ エラー C2262
ms.date: 11/04/2016
f1_keywords:
- C2262
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
ms.openlocfilehash: ef4cbeeeef9a7df42510dbf4cd021dde2081d294
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134577"
---
# <a name="compiler-error-c2262"></a>コンパイラ エラー C2262

'attribute_specifiers' : InternalsVisibleTo 宣言にバージョン、カルチャ、またはプロセッサ属性を指定することはできません

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性が正しく指定されていません。

## <a name="example"></a>例

次の例では C2262 が生成されます。

```cpp
// C2262.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262
[assembly: InternalsVisibleTo("assembly_name ")];   // OK
```
