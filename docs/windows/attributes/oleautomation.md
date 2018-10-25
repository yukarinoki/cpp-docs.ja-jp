---
title: oleautomation (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.oleautomation
dev_langs:
- C++
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ccc83dd6f51c3b7072b17d141f29e93c63688fa1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059533"
---
# <a name="oleautomation"></a>oleautomation

インターフェイスが Automation と互換性があることを示します。

## <a name="syntax"></a>構文

```cpp
[oleautomation]
```

## <a name="remarks"></a>Remarks

**Oleautomation** C++ 属性と同じ機能を持つ、 [oleautomation](/windows/desktop/Midl/oleautomation) MIDL 属性。

## <a name="example"></a>例

例を参照してください。 [defaultvalue](defaultvalue.md)と[nonextensible](nonextensible.md)の使用サンプル**oleautomation**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**dispinterface**|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)