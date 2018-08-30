---
title: v1_enum |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.v1_enum
dev_langs:
- C++
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbacec7644a05f0077c8d6ffbe3e7856c66dcc4f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222976"
---
# <a name="v1enum"></a>v1_enum

指定した列挙型を 16 ビットの既定ではなく、32 ビットのエンティティとして転送されることを指示します。

## <a name="syntax"></a>構文

```cpp
[v1_enum]
```

## <a name="remarks"></a>Remarks

**V1_enum** C++ 属性と同じ機能を持つ、 [v1_enum](/windows/desktop/Midl/v1-enum) MIDL 属性。

## <a name="example"></a>例

次のコードは、の使い方を示しています**v1_enum**:。

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1,
   e2 = 2
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|列挙型|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  