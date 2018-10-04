---
title: (C++ COM 属性) を非表示 |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.hidden
dev_langs:
- C++
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bfe3858070f4dbbd226d46479609f5d0a630956
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791775"
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

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、**クラス**、**構造体**メソッド、プロパティ|
|**反復可能**|いいえ|
|**必要な属性**|**コクラス**(に適用すると**クラス**または**構造体**)|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)  