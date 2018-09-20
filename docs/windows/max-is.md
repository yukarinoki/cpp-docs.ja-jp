---
title: max_is |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.max_is
dev_langs:
- C++
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a66a849dceb5ba28eb6630b513a121e219a3588
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432958"
---
# <a name="maxis"></a>max_is

有効な配列のインデックスの最大値を指定します。

## <a name="syntax"></a>構文

```cpp
[ max_is(
   "expression"
) ]
```

### <a name="parameters"></a>パラメーター

*式*<br/>
1 つ以上の C 言語の式。 空の引数スロットが許可されます。

## <a name="remarks"></a>Remarks

**Max_is** C++ 属性と同じ機能を持つ、 [max_is](/windows/desktop/Midl/max-is) MIDL 属性。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|フィールドに**構造体**または**共用体**パラメーターをインターフェイス、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**size_is**|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="example"></a>例

参照してください[first_is](../windows/first-is.md)配列のセクションを指定する方法の例についてはします。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](../windows/parameter-attributes.md)<br/>
[first_is](../windows/first-is.md)<br/>
[last_is](../windows/last-is.md)<br/>
[length_is](../windows/length-is.md)<br/>
[size_is](../windows/size-is.md)  