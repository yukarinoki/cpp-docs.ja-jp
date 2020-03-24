---
title: id (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 79e49b2c074cd82323c74489e33812c10c442c61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168058"
---
# <a name="id"></a>id

メンバー関数 (インターフェイスまたはディスパッチインターフェイスのプロパティまたはメソッド) の*dispid*パラメーターを指定します。

## <a name="syntax"></a>構文

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
インターフェイスメソッドのディスパッチ ID。

## <a name="remarks"></a>解説

**Id** C++属性には、 [id](/windows/win32/Midl/id) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Id**の使用方法の例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)
