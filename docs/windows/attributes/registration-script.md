---
description: '詳細については、次を参照してください: registration_script'
title: registration_script (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.registration_script
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
ms.openlocfilehash: 3722a799818c8ad76d710e4c570bc5fdd6b2e10c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327338"
---
# <a name="registration_script"></a>registration_script

指定されたカスタム登録スクリプトを実行します。

## <a name="syntax"></a>構文

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>パラメーター

*script*<br/>
カスタム登録スクリプト (.rgs) ファイルへの完全パス。 値が **none**(など) の `script = "none"` 場合、コクラスに登録要件がないことを示します。

## <a name="remarks"></a>解説

**Registration_script** C++ 属性は、*スクリプト* によって指定されたカスタム登録スクリプトを実行します。 この属性が指定されていない場合は、標準の .rgs ファイル (コンポーネントを登録するための情報を含む) が使用されます。 .Rgs ファイルの詳細については、「 [ATL レジストリコンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)」を参照してください。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。

## <a name="example"></a>例

次のコードでは、コンポーネントに cpp_attr_ref_registration_script .rgs というレジストリスクリプトがあることを指定しています。

```cpp
// cpp_attr_ref_registration_script.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="REG")];

[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]
__interface IFace {};

// requires "cpp_attr_ref_registration_script.rgs"
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]
class CMyClass:public IFace {};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|、、またはが1つ以上あり `coclass` `progid` `vi_progid` ます。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[rdx](rdx.md)
