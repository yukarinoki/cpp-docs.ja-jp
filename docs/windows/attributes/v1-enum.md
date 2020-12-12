---
description: '詳細については、次を参照してください: v1_enum'
title: v1_enum (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: c096ec78971e8980b68572c7f0bbb4510d03d3d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327201"
---
# <a name="v1_enum"></a>v1_enum

指定された列挙型を16ビットの既定値ではなく、32ビットのエンティティとして送信するように指示します。

## <a name="syntax"></a>構文

```cpp
[v1_enum]
```

## <a name="remarks"></a>解説

**V1_enum** C++ 属性には、 [v1_enum](/windows/win32/Midl/v1-enum) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **v1_enum** の使用方法を示しています。

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|列挙型|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)
