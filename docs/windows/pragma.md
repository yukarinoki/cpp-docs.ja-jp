---
title: プラグマ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pragma
dev_langs:
- C++
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f8ff470af7b7c825fb1c1dc7bf118e969a4b992
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603054"
---
# <a name="pragma"></a>pragma

引用符を使用せず、生成された .idl ファイルには、指定した文字列を出力します。

## <a name="syntax"></a>構文

```cpp
[ pragma(
   pragma_statement
) ];
```

### <a name="parameters"></a>パラメーター

*pragma_statement*  
このプラグマは、生成された .idl ファイルにアクセスしたいです。

## <a name="remarks"></a>Remarks

**プラグマ**C++ 属性と同じ機能を持つ、[プラグマ](http://msdn.microsoft.com/library/windows/desktop/aa367143)MIDL 属性。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[スタンドアロン属性](../windows/stand-alone-attributes.md)  
[pack](../preprocessor/pack.md)  