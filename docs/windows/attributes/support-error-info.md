---
title: support_error_info (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: e61ef2efbdc4039f496d7ffbcccc37cc8d111935
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166147"
---
# <a name="support_error_info"></a>support_error_info

詳細なエラーを返すためのサポートを実装します。

## <a name="syntax"></a>構文

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>パラメーター

*error_interface*<br/>
`IErrorInfo`を実装するインターフェイスの識別子。

## <a name="remarks"></a>解説

**support_error_info** C++ 属性は、ターゲット オブジェクトで発生した詳細なコンテキスト エラーをクライアントに返すためのサポートを実装します。 オブジェクトがエラーをサポートするには、オブジェクトによって `IErrorInfo` インターフェイスのメソッドが実装されている必要があります。 詳細については、「 [IDispatch と IErrorInfo のサポート](../../atl/supporting-idispatch-and-ierrorinfo.md)」を参照してください。

この属性により、 [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md) クラスが基本クラスとしてターゲット オブジェクトに追加されます。 この結果、`ISupportErrorInfo` の既定の実装が生成され、1つのインターフェイスがオブジェクトに対してエラーを生成するときに使用できます。

## <a name="example"></a>例

次のコードは、`ISupportErrorInfo` インターフェイスの既定のサポートを `CMyClass` オブジェクトに追加します。

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**class**|
|**反復可能**|はい|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)
