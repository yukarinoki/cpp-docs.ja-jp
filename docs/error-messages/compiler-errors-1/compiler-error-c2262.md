---
title: コンパイラ エラー C2262
ms.date: 11/04/2016
f1_keywords:
- C2262
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
ms.openlocfilehash: 12272c21adac0e326cb8b149b359584197577941
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397524"
---
# <a name="compiler-error-c2262"></a>コンパイラ エラー C2262

'attribute_specifiers' :InternalsVisibleTo 宣言に指定されたバージョン、カルチャ、またはプロセッサ アーキテクチャを持つことはできません。

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性が正しく指定されていません。

## <a name="example"></a>例

次の例では C2262 が生成されます。

```
// C2262.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262
[assembly: InternalsVisibleTo("assembly_name ")];   // OK
```