---
title: lcid (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: d97ad86e143102c96e87ae0a32245b0c01042501
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032434"
---
# <a name="lcid"></a>lcid

ロケール識別子を関数に渡すことができます。

## <a name="syntax"></a>構文

```cpp
[lcid]
```

## <a name="remarks"></a>Remarks

**Lcid**の機能を実装する C++ 属性、 [lcid](/windows/desktop/Midl/lcid) MIDL 属性。 ライブラリ ブロックのロケールを実装する場合は、使用、 **lcid =** `lcid`パラメーターを[モジュール](module-cpp.md)属性。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_lcid.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];
typedef long HRESULT;

[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]
__interface IStatic {
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス パラメーター|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)