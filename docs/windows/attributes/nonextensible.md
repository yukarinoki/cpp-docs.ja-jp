---
title: nonextensible (C++ COM の属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 332f61148ccf8cb5816e8bd347181ac9d130a730
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512451"
---
# <a name="nonextensible"></a>nonextensible

指定します、`IDispatch`実装にはプロパティのみが含まれていて、メソッドは、インターフェイスの説明に記載して、実行時にメンバーを追加して拡張することはできません。

## <a name="syntax"></a>構文

```cpp
[nonextensible]
```

## <a name="remarks"></a>Remarks

**Nonextensible** C++ 属性と同じ機能を持つ、 [nonextensible](/windows/desktop/Midl/nonextensible) MIDL 属性。

使用**nonextensible**も必要です、 [oleautomation](oleautomation.md)属性。

## <a name="example"></a>例

次のコードの用途の 1 つを示しています、 **nonextensible**属性。

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|`dual` `oleautomation`、または `dispinterface`|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)