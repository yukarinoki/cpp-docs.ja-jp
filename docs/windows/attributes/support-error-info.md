---
title: support_error_info (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c6bb07071efa162b5b33ae5f1dfe72ac7ea02e8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791270"
---
# <a name="supporterrorinfo"></a>support_error_info

詳細なエラーを返すためのサポートを実装します。

## <a name="syntax"></a>構文

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>パラメーター

*error_interface*<br/>
実装するインターフェイスの識別子`IErrorInfo`します。

## <a name="remarks"></a>Remarks

**support_error_info** C++ 属性は、ターゲット オブジェクトで発生した詳細なコンテキスト エラーをクライアントに返すためのサポートを実装します。 エラーのメソッドをサポートするために、オブジェクトの`IErrorInfo`オブジェクトでインターフェイスを実装する必要があります。 詳細については、次を参照してください。[サポート IDispatch と IErrorInfo](../../atl/supporting-idispatch-and-ierrorinfo.md)します。

この属性を追加、 [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)クラスとしてターゲット オブジェクトの基本クラス。 これは、結果の既定の実装、 `ISupportErrorInfo` 1 つのインターフェイスは、オブジェクトのエラーを生成するときに使用できます。

## <a name="example"></a>例

次のコードは、既定のサポートを追加、`ISupportErrorInfo`へのインターフェイス、`CMyClass`オブジェクト。

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

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**|
|**反復可能**|はい|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)  