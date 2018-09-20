---
title: auto_gcroot::swap |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr.auto_gcroot.swap
- msclr::auto_gcroot::swap
- auto_gcroot::swap
- auto_gcroot.swap
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot::swap
ms.assetid: 4915c629-6a53-432c-8155-3a7511dc70cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a34af7717de8d3920212c28c92da05007ec90a1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403631"
---
# <a name="autogcrootswap"></a>auto_gcroot::swap

別のオブジェクトを交換`auto_gcroot`します。

## <a name="syntax"></a>構文

```
void swap(
   auto_gcroot<_element_type> & _right
);
```

#### <a name="parameters"></a>パラメーター

*(_r)*<br/>
`auto_gcroot`交換先のオブジェクトします。

## <a name="example"></a>例

```
// msl_auto_gcroot_swap.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s1 = "string one";
   auto_gcroot<String^> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   s1.swap( s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[auto_gcroot のメンバー](../dotnet/auto-gcroot-members.md)<br/>
[swap 関数 (auto_gcroot)](../dotnet/swap-function-auto-gcroot.md)