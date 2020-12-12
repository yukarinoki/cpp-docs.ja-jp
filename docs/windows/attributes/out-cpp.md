---
description: '詳細情報: out (C++)'
title: out (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 1984d3bc539c5ad390cc1e507f2c8e3144d96ca2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329695"
---
# <a name="out-c"></a>out (C++)

呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。

## <a name="syntax"></a>構文

```cpp
[out]
```

## <a name="remarks"></a>解説

**out** C++ 属性には、 [propput](/windows/win32/Midl/out-idl) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

[out](bindable.md) の使用サンプルについては、「 **bindable**」の例を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|インターフェイス パラメーター|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[既定](defaultvalue.md)<br/>
[id](id.md)
