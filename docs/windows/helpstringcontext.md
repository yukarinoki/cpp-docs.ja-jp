---
title: helpstringcontext |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringcontext
dev_langs:
- C++
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 47afe841a2a8e4a1c41baf68dfd139a70b320c7d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394466"
---
# <a name="helpstringcontext"></a>helpstringcontext

.Hlp または .chm ファイルをヘルプ トピックの ID を指定します。

## <a name="syntax"></a>構文

```cpp
[ helpstringcontext(
   contextID
) ]
```

### <a name="parameters"></a>パラメーター

*contextID*<br/>
32 ビットのヘルプ コンテキスト識別子、**ヘルプ**ファイル。

## <a name="remarks"></a>Remarks

**Helpstringcontext** C++ 属性と同じ機能を持つ、 [helpstringcontext](/windows/desktop/Midl/helpstringcontext) ODL 属性。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object,
   helpstring("help string"),
   helpstringcontext(1),
   uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**インターフェイス**、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[インターフェイス属性](../windows/interface-attributes.md)<br/>
[クラス属性](../windows/class-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[モジュール](../windows/module-cpp.md)  