---
title: size_is |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.size_is
dev_langs:
- C++
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0505fde4ea92c643a6038d64d10ec06cda9cb60d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392334"
---
# <a name="sizeis"></a>size_is

メモリのサイズがサイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズを指定します。

## <a name="syntax"></a>構文

```cpp
[ size_is(
   "expression"
) ]
```

### <a name="parameters"></a>パラメーター

*式*<br/>
サイズのポインターに割り当てられたメモリのサイズ。

## <a name="remarks"></a>Remarks

**Size_is** C++ 属性と同じ機能を持つ、 [size_is](/windows/desktop/Midl/size-is) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[first_is](../windows/first-is.md)配列のセクションを指定する方法の例についてはします。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|フィールドに**構造体**または**共用体**パラメーターをインターフェイス、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`max_is`|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](../windows/parameter-attributes.md)<br/>
[first_is](../windows/first-is.md)<br/>
[last_is](../windows/last-is.md)<br/>
[max_is](../windows/max-is.md)<br/>
[length_is](../windows/length-is.md)  