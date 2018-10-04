---
title: 制限 (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1dfaed296242d2a0fc341c2ff5f137a08d753e71
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791235"
---
# <a name="restricted"></a>restricted

モジュール、インターフェイス、またはディスパッチ インターフェイスのメンバーを任意に呼び出すことはできませんを指定します。

## <a name="syntax"></a>構文

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>パラメーター

*interfaces*<br/>
COM オブジェクトに任意に呼ぶことが 1 つまたは複数のインターフェイス。 このパラメーターはクラスに適用される場合に有効です。

## <a name="remarks"></a>Remarks

**制限**C++ 属性と同じ機能を持つ、[制限](/windows/desktop/Midl/restricted)MIDL 属性。

## <a name="example"></a>例

次のコードを使用する方法を示しています、**制限**属性。

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスのメソッド、**インターフェイス**、**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**コクラス**(に適用すると**クラス**または**構造体**)|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[メソッド属性](method-attributes.md)  