---
title: pointer_default (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e8ddf566082bfded1f20a2bfe04e7cef0b5dc14
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791110"
---
# <a name="pointerdefault"></a>pointer_default

パラメーター リストに表示される最上位レベルのポインターを除く、すべてのポインターの既定のポインターの属性を指定します。

## <a name="syntax"></a>構文

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>パラメーター

*値*<br/>
ポインター型を記述する値: **ptr**、 **ref**、または**一意**します。

## <a name="remarks"></a>Remarks

**Pointer_default** C++ 属性と同じ機能を持つ、 [pointer_default](/windows/desktop/Midl/pointer-default) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[defaultvalue](defaultvalue.md)の使用サンプル**pointer_default**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)  