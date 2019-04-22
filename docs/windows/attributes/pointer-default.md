---
title: pointer_default (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: 37bd2b16fb7a7c1c186f59897898e08cc73fffae
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022667"
---
# <a name="pointerdefault"></a>pointer_default

パラメーター リストに表示される最上位レベルのポインターを除く、すべてのポインターの既定のポインターの属性を指定します。

## <a name="syntax"></a>構文

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>パラメーター

*value*<br/>
ポインター型を記述する値: **ptr**、 **ref**、または**一意**します。

## <a name="remarks"></a>Remarks

**Pointer_default** C++属性と同じ機能を持つ、 [pointer_default](/windows/desktop/Midl/pointer-default) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[defaultvalue](defaultvalue.md)の使用サンプル**pointer_default**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)