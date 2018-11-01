---
title: public (C++ 属性) (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: d89df014beae5a62a035c3156b92d3337ecd2c14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579336"
---
# <a name="public-c-attributes"></a>public (C++ 属性)

.Idl ファイル内から参照されていない場合でも、typedef がタイプ ライブラリに送られるようにします。

## <a name="syntax"></a>構文

```cpp
[public]
```

## <a name="remarks"></a>Remarks

**パブリック**C++ 属性と同じ機能を持つ、[パブリック](/windows/desktop/Midl/public)MIDL 属性。

## <a name="example"></a>例

次のコードを使用する方法を示しています、**パブリック**属性。

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**typedef**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)