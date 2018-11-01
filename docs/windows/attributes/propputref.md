---
title: propputref (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: 0ebf39be6d83e7c5a64ad29f34f9accf0743dbf4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551282"
---
# <a name="propputref"></a>propputref

値の代わりに参照を使用するプロパティ設定関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propputref]
```

## <a name="remarks"></a>Remarks

**Propputref** C++ 属性と同じ機能を持つ、 [propputref](/windows/desktop/Midl/propputref) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](bindable.md)の使用サンプル**propputref**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propget`, `propput`|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)