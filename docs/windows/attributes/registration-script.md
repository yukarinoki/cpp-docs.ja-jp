---
title: registration_script (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: edc9d5aa1d7c49de34ee3dbb02d2a55542962a50
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791810"
---
# <a name="registrationscript"></a>registration_script

指定したカスタム登録スクリプトを実行します。

## <a name="syntax"></a>構文

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>パラメーター

*スクリプト*<br/>
カスタム登録スクリプト (.rgs) ファイルの完全パスです。 値**none**など`script = "none"`コクラスに登録要件がないことを示します。

## <a name="remarks"></a>Remarks

**Registration_script** C++ 属性で指定されたカスタムの登録スクリプトを実行する*スクリプト*します。 この属性が指定されていない場合は、(コンポーネントを登録するための情報を含む) 標準 .rgs ファイルが使用されます。 .Rgs ファイルの詳細については、次を参照してください。 [、ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。

この属性では、する必要があります、[コクラス](coclass.md)、 [progid](progid.md)、または[vi_progid](vi-progid.md)属性 (またはこれらのいずれかを意味する別の属性) も適用が同じ要素をします。

## <a name="example"></a>例

次のコードでは、コンポーネントに cpp_attr_ref_registration_script.rgs をという名前のレジストリ スクリプトがあることを指定します。

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

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[rdx](rdx.md)  