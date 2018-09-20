---
title: noncreatable |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.noncreatable
dev_langs:
- C++
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 559d461a996789986dcc445d6ef510c7b179542c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381297"
---
# <a name="noncreatable"></a>noncreatable

単独でインスタンス化できないオブジェクトを定義します。

## <a name="syntax"></a>構文

```cpp
[noncreatable]
```

## <a name="remarks"></a>Remarks

**Noncreatable** C++ 属性と同じ機能を持つ、 [noncreatable](/windows/desktop/Midl/noncreatable) MIDL 属性と、生成されたに自動的に渡されます。コンパイラによって IDL ファイルです。

この属性が ATL を使用するプロジェクト内で使用される場合、属性の動作を変更します。 上記の動作に加え、属性もは挿入、[役立つ](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)マクロ。 このマクロは atl オブジェクトを外部で作成できないことを示します。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_noncreatable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("11111111-1111-1111-1111-111111111111")]
__interface A
{
};

[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]
class CMyClass : public A
{
   HRESULT xx();
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[クラス属性](../windows/class-attributes.md)  
