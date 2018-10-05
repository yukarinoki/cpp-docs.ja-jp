---
title: iid_is (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.iid_is
dev_langs:
- C++
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ec9bb1a35b1ce049dfeca7b356b98431fad4578
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792050"
---
# <a name="iidis"></a>iid_is

インターフェイス ポインターによって示される COM インターフェイスの IID を指定します。

## <a name="syntax"></a>構文

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>パラメーター

*式*<br/>
インターフェイス ポインターが指す COM インターフェイスの IID を指定する C 言語の式。

## <a name="remarks"></a>Remarks

**Iid_is** C++ 属性と同じ機能を持つ、 [iid_is](/windows/desktop/Midl/iid-is) MIDL 属性。

## <a name="example"></a>例

次のコードを使用する示します**iid_is**:

```cpp
// cpp_attr_ref_iid_is.cpp
// compile with: /LD
#include "wtypes.h"
#include "unknwn.h"
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]
   IUnknown ** ppvObject);
};

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスのパラメーター、データ メンバー|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)  