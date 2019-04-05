---
title: async_uuid (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.async_uuid
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
ms.openlocfilehash: 4c2bca9165d8b23f8cfa4f0f5523c882fd2f52bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035797"
---
# <a name="asyncuuid"></a>async_uuid

同期および非同期の両方のバージョンの COM インターフェイスを定義する、MIDL コンパイラに指示する UUID を指定します。

## <a name="syntax"></a>構文

```cpp
[async_uuid (uuid)]
```

### <a name="parameters"></a>パラメーター

*uuid*<br/>
インターフェイスのバージョンを識別するための UUID。

## <a name="remarks"></a>Remarks

**Async_uuid** C++ 属性と同じ機能を持つ、 [async_uuid](/windows/desktop/Midl/async-uuid) MIDL 属性。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_async_uuid.cpp
// compile with: /LD
#include <Windows.h>
[module(name="Test")];
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|`interface`|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**デュアル**、**ディスパッチ インターフェイス**|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)