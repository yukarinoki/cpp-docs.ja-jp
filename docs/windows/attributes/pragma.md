---
description: '詳細情報: プラグマ'
title: pragma (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: 1c9b9313b05d5f6b6123189b823ef750cb7c16a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327399"
---
# <a name="pragma"></a>pragma

指定された文字列を、引用符を使用せずに、生成された .idl ファイルに出力します。

## <a name="syntax"></a>構文

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>パラメーター

*pragma_statement*<br/>
生成された .idl ファイルに含めるプラグマ。

## <a name="remarks"></a>解説

**プラグマ** C++ 属性には、 [pragma](/windows/win32/Midl/pragma) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)
