---
title: length_is (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: 54206dd82a550924169bf7bcccd4f70f9e5a657c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489561"
---
# <a name="lengthis"></a>length_is

転送する配列要素の数を指定します。

## <a name="syntax"></a>構文

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>パラメーター

*式*<br/>
1 つ以上の C 言語の式。 空の引数スロットが許可されます。

## <a name="remarks"></a>Remarks

**Length_is** C++ 属性と同じ機能を持つ、 [length_is](/windows/desktop/Midl/length-is) MIDL 属性。

## <a name="example"></a>例

参照してください[first_is](first-is.md)配列のセクションを指定する方法の例についてはします。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|フィールドに**構造体**または**共用体**パラメーターをインターフェイス、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)