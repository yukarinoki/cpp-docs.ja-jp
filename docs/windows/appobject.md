---
title: appobject |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.appobject
dev_langs:
- C++
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8de7bbfb2f00f5e1a909a83a5399e2d564747962
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213996"
---
# <a name="appobject"></a>appobject

完全な .exe アプリケーションに関連付けられ、関数と、コクラスのプロパティがこのグローバルに利用できることを示しますアプリケーション オブジェクトとしてコクラスを識別する[タイプ ライブラリ](../mfc/automation-clients-using-type-libraries.md)します。

## <a name="syntax"></a>構文

```cpp
[appobject]
```

## <a name="remarks"></a>Remarks

**Appobject** C++ 属性と同じ機能を持つ、 [appobject](/windows/desktop/Midl/appobject) MIDL 属性。

## <a name="example"></a>例

次のコードは単純なクラス定義を含む属性ブロックに続く**appobject**:

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|`coclass`|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[クラス属性](../windows/class-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  