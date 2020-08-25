---
title: v1_enum (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: 6529a32b0bfe2de09191e9cced8f6bd98e7ffdcc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832985"
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

次のコードは、 **v1_enum**の使用方法を示しています。

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>必要条件

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
