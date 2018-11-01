---
title: requestedit (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requestedit
helpviewer_keywords:
- requestedit attribute
ms.assetid: b3c24790-3c4a-4646-8722-03d7b51172ee
ms.openlocfilehash: 27e6190cbb5908d46150acb758e2b4d5efaff1bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611590"
---
# <a name="requestedit"></a>requestedit

プロパティをサポートしていることを示します、`OnRequestEdit`通知します。

## <a name="syntax"></a>構文

```cpp
[requestedit]
```

## <a name="remarks"></a>Remarks

**Requestedit** C++ 属性と同じ機能を持つ、 [requestedit](/windows/desktop/Midl/requestedit) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](bindable.md)の使用サンプル**requestedit**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)