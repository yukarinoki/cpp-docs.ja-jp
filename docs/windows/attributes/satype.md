---
title: satype (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 4619deec6d5e4e9083fbc7bcab53caee0101285c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166277"
---
# <a name="satype"></a>satype

`SAFEARRAY` 構造体のデータ型を指定します。

## <a name="syntax"></a>構文

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>パラメーター

*data_type*<br/>
インターフェイスメソッドにパラメーターとして渡される `SAFEARRAY` データ構造体のデータ型。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスパラメーター、インターフェイスメソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

## <a name="remarks"></a>解説

**Satype** C++属性は、`SAFEARRAY`のデータ型を指定します。

> [!NOTE]
> 生成された .idl ファイル内の `SAFEARRAY` ポインターから、.cpp ファイルでの宣言方法から間接参照のレベルが削除されます。

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

## <a name="see-also"></a>参照

[コンパイラ属性](compiler-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[id](id.md)
