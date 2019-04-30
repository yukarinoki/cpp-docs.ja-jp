---
title: max_is (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: dca2a3dc18aa3c3e75bbb682ed0b1b90adcd9236
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409279"
---
# <a name="maxis"></a>max_is

有効な配列のインデックスの最大値を指定します。

## <a name="syntax"></a>構文

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>パラメーター

*式 (expression)*<br/>
1 つ以上の C 言語の式。 空の引数スロットが許可されます。

## <a name="remarks"></a>Remarks

**Max_is** C++属性と同じ機能を持つ、 [max_is](/windows/desktop/Midl/max-is) MIDL 属性。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|フィールドに**構造体**または**共用体**パラメーターをインターフェイス、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**size_is**|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="example"></a>例

参照してください[first_is](first-is.md)配列のセクションを指定する方法の例についてはします。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)