---
title: バージョン (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: fe1df9e12b9adbf9ce55978fd3479f7e740ddc96
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025753"
---
# <a name="version-c"></a>version (C++)

クラスの複数のバージョン間で特定のバージョンを識別します。

## <a name="syntax"></a>構文

```cpp
[ version("version") ]
```

### <a name="parameters"></a>パラメーター

*version*<br/>
バージョン番号、`coclass`します。 指定しない場合、1.0 は .idl ファイルに配置されます。

## <a name="remarks"></a>Remarks

**バージョン**C++ 属性と同じ機能を持つ、[バージョン](/windows/desktop/Midl/version)MIDL 属性と、生成された .idl ファイルに渡されます。

## <a name="example"></a>例

参照してください、[バインド可能な](bindable.md)の使用サンプルの例を**バージョン**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[クラス属性](class-attributes.md)