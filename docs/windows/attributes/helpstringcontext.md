---
title: helpstringcontext (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: e6d4a6b4ab2381fc9ebe0f237978c92fe0f656c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224449"
---
# <a name="helpstringcontext"></a>helpstringcontext

.Hlp または .chm ファイルのヘルプトピックの ID を指定します。

## <a name="syntax"></a>構文

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>パラメーター

*contextID*<br/>
**ヘルプ**ファイル内の32ビットのヘルプコンテキスト識別子。

## <a name="remarks"></a>解説

**Helpstringcontext** C++ 属性には、 [helpstringcontext](/windows/win32/Midl/helpstringcontext) ODL 属性と同じ機能があります。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`class`**、 **interface**、interface メソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[第](module-cpp.md)
