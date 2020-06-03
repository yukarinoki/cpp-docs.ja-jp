---
title: propget (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: d2c0ebab1630634ddd4fc81e7c9c8364f7fad46f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166460"
---
# <a name="propget"></a>propget

プロパティアクセサー関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propget]
```

## <a name="remarks"></a>解説

**Propget** C++属性には、 [propget](/windows/win32/Midl/propget) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Propget**の使用例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|方法|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propput`, `propputref`|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)
