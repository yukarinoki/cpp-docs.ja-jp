---
title: out (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: b99e520a11c2e8110d2e63fa85ddb1dd444e56e6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837100"
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

## <a name="requirements"></a>必要条件

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
