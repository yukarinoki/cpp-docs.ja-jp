---
title: 読み取り専用 (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8cba3c15049c176b19f0da197d19017ae2aa699d
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791743"
---
# <a name="readonly-c"></a>readonly (C++)

データ メンバーへの割り当てを禁止します。

## <a name="syntax"></a>構文

```cpp
[readonly]
```

## <a name="remarks"></a>Remarks

**Readonly** C++ 属性と同じ機能を持つ、 [readonly](/windows/desktop/Midl/readonly) MIDL 属性。

メソッドのパラメーターの変更を禁止する場合を使用し、[で](in-cpp.md)属性。

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

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)  