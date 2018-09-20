---
title: propget |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propget
dev_langs:
- C++
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d5a145c730104608bd8b1709191fef32d3bfc08
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380753"
---
# <a name="propget"></a>propget

プロパティのアクセサー関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propget]
```

## <a name="remarks"></a>Remarks

**Propget** C++ 属性と同じ機能を持つ、 [propget](/windows/desktop/Midl/propget) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](../windows/bindable.md)の使用サンプル**propget**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propput`, `propputref`|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[propput](../windows/propput.md)<br/>
[propputref](../windows/propputref.md)  