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
ms.openlocfilehash: 994a4a48c5199c3efb05a00331656b3b23a2a0c0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067043"
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