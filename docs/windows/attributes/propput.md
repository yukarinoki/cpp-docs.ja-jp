---
title: propput (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: 8817d0042c3055b5bbf9b111e6f02b9d9a4c152c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166446"
---
# <a name="propput"></a>propput

プロパティ設定関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propput]
```

## <a name="remarks"></a>解説

**Propput** C++属性には、 [propput](/windows/win32/Midl/propput) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Propput**の使用例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|方法|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propget`, `propputref`|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)
