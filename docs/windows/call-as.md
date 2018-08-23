---
title: call_as |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b5fffe1490587e36d39a959f75796093cbc32a0f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601995"
---
# <a name="callas"></a>call_as

により、[ローカル](../windows/local-cpp.md)リモート関数が呼び出されると、ローカル関数が呼び出されるように、リモート関数にマップする関数。

## <a name="syntax"></a>構文

```cpp
[ call_as(
   function
) ]
```

### <a name="parameters"></a>パラメーター

*function*  
ローカル関数をリモート関数を呼び出すときに呼び出されます。

## <a name="remarks"></a>Remarks

**Call_as** C++ 属性と同じ機能を持つ、 [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL 属性。

## <a name="example"></a>例

次のコードを使用する方法を示しています。 **call_as**リモート処理不可能関数をマップする (`f1`) リモート処理可能な関数に (`Remf1`)。

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[local](../windows/local-cpp.md)  