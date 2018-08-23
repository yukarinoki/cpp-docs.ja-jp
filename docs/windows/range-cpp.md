---
title: 範囲 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.range
dev_langs:
- C++
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c1ad17b6f658129ff33be28843ebb48b86f7845
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599628"
---
# <a name="range-c"></a>range (C++)

引数または値を持つが実行時に設定されているフィールドに使用できる値の範囲を指定します。

## <a name="syntax"></a>構文

```cpp
[ range(
   low,
   high
) ]
```

### <a name="parameters"></a>パラメーター

*low*  
範囲の下限値。

*high*  
範囲の上限値。

## <a name="remarks"></a>Remarks

**範囲**C++ 属性と同じ機能を持つ、[範囲](http://msdn.microsoft.com/library/windows/desktop/aa367151)MIDL 属性。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_range.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスのメソッド、インターフェイス パラメーター|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[パラメーター属性](../windows/parameter-attributes.md)  
[データ メンバー属性](../windows/data-member-attributes.md)  