---
description: 詳細については、「satype を参照してください。
title: satype (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: dab0f866eba5501a9a83d531d9cbdf50501dcff0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327312"
---
# <a name="satype"></a>satype

構造体のデータ型を指定し `SAFEARRAY` ます。

## <a name="syntax"></a>構文

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>パラメーター

*data_type*<br/>
`SAFEARRAY`インターフェイスメソッドにパラメーターとして渡されるデータ構造体のデータ型。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|インターフェイスパラメーター、インターフェイスメソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

## <a name="remarks"></a>解説

**Satype** C++ 属性は、のデータ型を指定し `SAFEARRAY` ます。

> [!NOTE]
> `SAFEARRAY`生成された .idl ファイル内のポインターから、.cpp ファイルでの宣言方法から間接参照のレベルが削除されます。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[id](id.md)
