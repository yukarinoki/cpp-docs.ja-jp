---
description: '詳細については、次を参照してください: pointer_default'
title: pointer_default (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: 0c7768227a5922bca7e1b48b3ad82821bb62ea54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329685"
---
# <a name="pointer_default"></a>pointer_default

パラメーターリストに表示されるトップレベルのポインターを除く、すべてのポインターの既定のポインター属性を指定します。

## <a name="syntax"></a>構文

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>パラメーター

*value*<br/>
ポインターの種類として **ptr**、 **ref**、または **unique** を示す値。

## <a name="remarks"></a>解説

**Pointer_default** C++ 属性には、 [pointer_default](/windows/win32/Midl/pointer-default) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Pointer_default** の使用例については、 [defaultvalue](defaultvalue.md)の例を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)
