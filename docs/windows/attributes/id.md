---
title: id (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a17edd3ec3c35c307ca35a6657c69f3f7fef246a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791175"
---
# <a name="id"></a>ID

指定します、 *dispid* (プロパティまたはメソッド、インターフェイスまたは dispinterface) のメンバー関数のパラメーター。

## <a name="syntax"></a>構文

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
インターフェイス メソッドのディスパッチ ID。

## <a name="remarks"></a>Remarks

**Id** C++ 属性と同じ機能を持つ、 [id](/windows/desktop/Midl/id) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](bindable.md)を使用する方法の例については**id**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)  