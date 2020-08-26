---
title: version (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 7d21761a556455cec27087896984bdc721841d9d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832946"
---
# <a name="version-c"></a>version (C++)

クラスの複数のバージョン間で特定のバージョンを識別します。

## <a name="syntax"></a>構文

```cpp
[ version("version") ]
```

### <a name="parameters"></a>パラメーター

*version*<br/>
`coclass` のバージョン番号。 指定しない場合、1.0 は .idl ファイルに配置されます。

## <a name="remarks"></a>解説

**Version** C++ 属性には[バージョン](/windows/win32/Midl/version)MIDL 属性と同じ機能があり、生成された .idl ファイルに渡されます。

## <a name="example"></a>例

**バージョン**の使用例については、[バインド](bindable.md)可能な例を参照してください。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[クラス属性](class-attributes.md)
