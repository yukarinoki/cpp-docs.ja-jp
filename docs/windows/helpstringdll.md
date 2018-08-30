---
title: helpstringdll |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringdll
dev_langs:
- C++
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bc10f86a8fa646a1072de8b7c5e30121d98750cf
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219953"
---
# <a name="helpstringdll"></a>typelib

使用してドキュメントの文字列の検索 (ローカライズ) を実行する DLL の名前を指定します。

## <a name="syntax"></a>構文

```cpp
[ helpstringdll(
   "string"
) ]
```

### <a name="parameters"></a>パラメーター

*string*  
使用してドキュメントの文字列の検索を実行する DLL です。

## <a name="remarks"></a>Remarks

**Helpstringdll** C++ 属性と同じ機能を持つ、 [helpstringdll](/windows/desktop/Midl/helpstringdll) MIDL 属性。

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

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**インターフェイス**、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[インターフェイス属性](../windows/interface-attributes.md)  
[クラス属性](../windows/class-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  