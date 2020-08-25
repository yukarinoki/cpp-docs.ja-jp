---
title: 非拡張 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 01f89c4a06a8e90fd6a539fa5a5a85ebb8067d40
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833037"
---
# <a name="nonextensible"></a>nonextensible

実装に、 `IDispatch` インターフェイスの説明に示されているプロパティとメソッドのみが含まれ、実行時に追加のメンバーで拡張できないことを指定します。

## <a name="syntax"></a>構文

```cpp
[nonextensible]
```

## <a name="remarks"></a>解説

**非拡張**C++ 属性には、[非拡張](/windows/win32/Midl/nonextensible)MIDL 属性と同じ機能があります。

**非拡張**を使用する場合は、 [oleautomation](oleautomation.md)属性も必要です。

## <a name="example"></a>例

次のコードは、 **非拡張** 属性の使用方法を示しています。

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

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**|
|**Repeatable**|いいえ|
|**必須属性**|`dual` and `oleautomation` 、or `dispinterface`|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)
