---
title: helpstringdll (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 4ec0d959b2fc10fc34bfc7050a1970359dae5bbc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168123"
---
# <a name="helpstringdll"></a>typelib

ドキュメント文字列参照 (ローカライズ) を実行するために使用する DLL の名前を指定します。

## <a name="syntax"></a>構文

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>パラメーター

*string*<br/>
ドキュメント文字列検索を実行するために使用する DLL。

## <a name="remarks"></a>解説

**Helpstringdll** C++属性には、 [helpstringdll](/windows/win32/Midl/helpstringdll) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**インターフェイス**、インターフェイスメソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)
