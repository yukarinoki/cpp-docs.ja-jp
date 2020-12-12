---
description: '詳細情報: オプション (C++)'
title: 省略可能 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: 70ae49854a496aad35edc87bdd1ac5facb899448
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329732"
---
# <a name="optional-c"></a>optional (C++)

メンバー関数の省略可能なパラメーターを指定します。

## <a name="syntax"></a>構文

```cpp
[optional]
```

## <a name="remarks"></a>解説

**省略可能** な C++ 属性には、[省略可能](/windows/win32/Midl/optional)な MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **オプション** を使用する方法を示しています。

```cpp
// cpp_attr_ref_optional.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] long procedure ([in, optional] VARIANT i);
};
```

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
[パラメーター属性](parameter-attributes.md)
