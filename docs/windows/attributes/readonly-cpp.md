---
title: readonly (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: ea2b0a46d34fc415a3b9eca97b92cda764fc7d42
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839804"
---
# <a name="readonly-c"></a>readonly (C++)

データ メンバーへの割り当てを禁止します。

## <a name="syntax"></a>構文

```cpp
[readonly]
```

## <a name="remarks"></a>解説

**readonly** C++ 属性には、 [readonly](/windows/win32/Midl/readonly) MIDL 属性と同じ機能があります。

メソッド パラメーターの変更を禁止する場合は、 [in](in-cpp.md) 属性を使用します。

## <a name="example"></a>例

**readonly** 属性の使用方法は、次のコードのとおりです。

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
};
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|インターフェイス メソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[データメンバー属性](data-member-attributes.md)
