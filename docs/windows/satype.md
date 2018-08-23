---
title: satype |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 462dba3caaef53e49203eab6d006ea59d7b23c0e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590374"
---
# <a name="satype"></a>satype

データ型を指定します、`SAFEARRAY`構造体。

## <a name="syntax"></a>構文

```cpp
[ satype(
   data_type
) ]
```

### <a name="parameters"></a>パラメーター

*data_type*  
データ型、`SAFEARRAY`インターフェイス メソッドにパラメーターとして渡されるデータ構造体。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスのパラメーター、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

## <a name="remarks"></a>Remarks

**Satype** C++ 属性のデータ型を指定します、`SAFEARRAY`します。

> [!NOTE]
> レベルの間接参照が削除される、 `SAFEARRAY` .cpp ファイルで宣言されている方法から生成された .idl ファイル内のポインター。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>関連項目

[コンパイラ属性](../windows/compiler-attributes.md)  
[パラメーター属性](../windows/parameter-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[ID](../windows/id.md)  