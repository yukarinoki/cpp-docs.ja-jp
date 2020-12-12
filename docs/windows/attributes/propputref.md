---
description: '詳細情報: propputref'
title: propputref (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: 5f09d742ef0df75df03e4f4d740181cfcaaa8f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329671"
---
# <a name="propputref"></a>propputref

値ではなく参照を使用するプロパティ設定関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propputref]
```

## <a name="remarks"></a>解説

**Propputref** C++ 属性には、 [propputref](/windows/win32/Midl/propputref) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Propputref** の使用例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|Method|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|`propget`, `propput`|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)
