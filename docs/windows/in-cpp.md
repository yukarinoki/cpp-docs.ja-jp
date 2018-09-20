---
title: (c++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.in
dev_langs:
- C++
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd6b79d84e4737cdbeb670bdd31b8cacf35cf8f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373388"
---
# <a name="in-c"></a>in (C++)

呼び出し元のプロシージャから呼び出されたプロシージャに渡されるパラメーターがあることを示します。

## <a name="syntax"></a>構文

```cpp
[in]
```

## <a name="remarks"></a>Remarks

**で**C++ 属性と同じ機能を持つ、[で](/windows/desktop/Midl/in)MIDL 属性。

## <a name="example"></a>例

参照してください[バインド可能な](../windows/bindable.md)を使用する方法の例については**で**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスのパラメーター、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**retval**|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[パラメーター属性](../windows/parameter-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[defaultvalue](../windows/defaultvalue.md)<br/>
[ID](../windows/id.md)<br/>
[out](../windows/out-cpp.md)  