---
title: (C++ COM 属性) を非表示
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: d1d87ea057b22984a0e0f8f5518899e36f7d0221
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038422"
---
# <a name="hidden"></a>hidden

項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。

## <a name="syntax"></a>構文

```cpp
[hidden]
```

## <a name="remarks"></a>Remarks

**隠し**C++ 属性と同じ機能を持つ、[隠し](/windows/desktop/Midl/hidden)MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](bindable.md)を使用する方法の例については**隠し**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、**クラス**、**構造体**メソッド、プロパティ|
|**反復可能**|いいえ|
|**必要な属性**|**コクラス**(に適用すると**クラス**または**構造体**)|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)