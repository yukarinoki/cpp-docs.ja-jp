---
title: readonly (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 415ad5e33de3132e055e53178e6e65d411f169f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214605"
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

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)
