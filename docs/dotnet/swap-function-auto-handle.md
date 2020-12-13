---
description: '詳細情報: swap 関数 (auto_handle)'
title: swap 関数 (auto_handle)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- swap function
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
ms.openlocfilehash: 24e3ad0d80cb747ddff116682cb9760b29ccc893
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335287"
---
# <a name="swap-function-auto_handle"></a>swap 関数 (auto_handle)

オブジェクトを相互に交換 `auto_handle` します。

## <a name="syntax"></a>構文

```
template<typename _element_type>
void swap(
   auto_handle<_element_type> % _left,
   auto_handle<_element_type> % _right
);
```

#### <a name="parameters"></a>パラメーター

*_left*<br/>
`auto_handle`。

*_right*<br/>
別の `auto_handle`。

## <a name="example"></a>例

```cpp
// msl_swap_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1 = "string one";
   auto_handle<String> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   swap( s1, s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\auto_handle.h>

**名前空間** msclr

## <a name="see-also"></a>関連項目

[auto_handle](../dotnet/auto-handle.md)<br/>
[auto_handle::swap](./auto-handle-class.md#swap)
