---
title: id (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 5faf08418771deda3086a434cff6b1900a37e36e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034697"
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

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)