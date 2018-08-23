---
title: support_error_info |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 68cfd7eb96cbf19f5675cec17a9270b9b37b2105
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599820"
---
# <a name="supporterrorinfo"></a>support_error_info

詳細なエラーを返すためのサポートを実装します。

## <a name="syntax"></a>構文

```cpp
[ support_error_info(
   error_interface=uuid
) ]
```

### <a name="parameters"></a>パラメーター

*error_interface*  
実装するインターフェイスの識別子`IErrorInfo`します。

## <a name="remarks"></a>Remarks

**support_error_info** C++ 属性は、ターゲット オブジェクトで発生した詳細なコンテキスト エラーをクライアントに返すためのサポートを実装します。 エラーのメソッドをサポートするために、オブジェクトの`IErrorInfo`オブジェクトでインターフェイスを実装する必要があります。 詳細については、「 [IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)」を参照してください。

この属性により、 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) クラスが基本クラスとしてターゲット オブジェクトに追加されます。 これは、結果の既定の実装、 `ISupportErrorInfo` 1 つのインターフェイスは、オブジェクトのエラーを生成するときに使用できます。

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
|**反復可能**|[はい]|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](../windows/com-attributes.md)  
[クラス属性](../windows/class-attributes.md)  