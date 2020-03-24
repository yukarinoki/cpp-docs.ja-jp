---
title: in (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: f25f15148621d7092858577825dbdd6caa1ae0be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166797"
---
# <a name="in-c"></a>in (C++)

呼び出し元プロシージャから呼び出されたプロシージャにパラメーターが渡されることを示します。

## <a name="syntax"></a>構文

```cpp
[in]
```

## <a name="remarks"></a>解説

**In** C++属性には[、MIDL 属性のと](/windows/win32/Midl/in)同じ機能があります。

## <a name="example"></a>例

**で**を使用する方法の例については、「[バインド](bindable.md)可能」を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスパラメーター、インターフェイスメソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**retval**|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)<br/>
[out](out-cpp.md)
