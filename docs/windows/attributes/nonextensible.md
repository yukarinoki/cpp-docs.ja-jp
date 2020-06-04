---
title: 非拡張 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 2a1cd4d685e2fd141c6e11feaea488f44a884c80
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214683"
---
# <a name="nonextensible"></a>nonextensible

`IDispatch` の実装に、インターフェイスの説明に示されているプロパティとメソッドのみが含まれ、実行時に追加のメンバーで拡張できないことを指定します。

## <a name="syntax"></a>構文

```cpp
[nonextensible]
```

## <a name="remarks"></a>解説

**非拡張** C++属性には、[非拡張](/windows/win32/Midl/nonextensible)MIDL 属性と同じ機能があります。

**非拡張**を使用する場合は、 [oleautomation](oleautomation.md)属性も必要です。

## <a name="example"></a>例

次のコードは、**非拡張**属性の使用方法を示しています。

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
|**必要な属性**|`dual` と `oleautomation`、または `dispinterface`|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)
