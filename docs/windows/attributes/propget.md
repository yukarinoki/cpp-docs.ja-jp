---
title: propget (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: 495c6e974bbe226a77d5685c7d1d8adb29e30830
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646001"
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

例をご覧ください[バインド可能な](bindable.md)の使用サンプル**propget**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propput`, `propputref`|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)