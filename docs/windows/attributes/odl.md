---
title: odl (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.odl
helpviewer_keywords:
- odl attribute
ms.assetid: 75dcb314-b50f-4a63-9180-507ac1bc78f3
ms.openlocfilehash: 2627be876f0c46bb7d72c2c6b825cf76e24b1eb1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214735"
---
# <a name="odl"></a>odl

オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。 MIDL コンパイラでは、 **odl**属性は必要ありません。これは、古い odl ファイルとの互換性のためにのみ認識されます。

## <a name="syntax"></a>構文

```cpp
[odl]
```

## <a name="remarks"></a>解説

**Odl** C++属性には、 [odl](/windows/win32/Midl/odl) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_odl.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLIb")];

[odl, oleautomation, dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyInterface
{
   HRESULT x();
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
class cmyClass : public IMyInterface
{
public:
   HRESULT x(){}
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)
