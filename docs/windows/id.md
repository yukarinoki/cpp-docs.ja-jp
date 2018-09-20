---
title: id |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 13ddef5b6bb83de16c72438e2b9f2bb3d4e8d635
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386354"
---
# <a name="id"></a>ID

指定します、 *dispid* (プロパティまたはメソッド、インターフェイスまたは dispinterface) のメンバー関数のパラメーター。

## <a name="syntax"></a>構文

```cpp
[ id(
   dispid
) ]
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
インターフェイス メソッドのディスパッチ ID。

## <a name="remarks"></a>Remarks

**Id** C++ 属性と同じ機能を持つ、 [id](/windows/desktop/Midl/id) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](../windows/bindable.md)を使用する方法の例については**id**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[データ メンバー属性](../windows/data-member-attributes.md)<br/>
[defaultvalue](../windows/defaultvalue.md)<br/>
[in](../windows/in-cpp.md)<br/>
[out](../windows/out-cpp.md)  