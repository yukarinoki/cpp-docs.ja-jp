---
description: '詳細情報: include (C++)'
title: include (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: c6d12b9d8826ce84de0c01aaf055f5a4176fea10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321364"
---
# <a name="include-c"></a>include (C++)

生成される .idl ファイルに含める1つ以上のヘッダーファイルを指定します。

## <a name="syntax"></a>構文

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>パラメーター

*header_file*<br/>
生成された .idl ファイルに追加するファイルの名前。

## <a name="remarks"></a>解説

**Include** C++ 属性により、 `#include` 生成された .idl ファイル内のステートメントの下にステートメントが配置され `import "docobj.idl"` ます。

**Include** C++ 属性には、 [include](/windows/win32/Midl/include) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **include** を使用する方法の例を示しています。 この例では、ファイルにはステートメントだけが含まれています。 `#include`

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)
