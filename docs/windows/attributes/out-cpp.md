---
title: out (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.out
dev_langs:
- C++
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbb7bc07ab3b3942f1a3a6fa20c69327c0bd1a53
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063758"
---
# <a name="out-c"></a>out (C++)

呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。

## <a name="syntax"></a>構文

```cpp
[out]
```

## <a name="remarks"></a>Remarks

**out** C++ 属性には、 [propput](/windows/desktop/Midl/out-idl) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

[out](bindable.md) の使用サンプルについては、「 **bindable**」の例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス パラメーター|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[ID](id.md)