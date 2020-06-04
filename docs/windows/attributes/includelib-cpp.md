---
title: インクルード (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 4022a3f1f2d4ccaabe65c24065be8e1c846d604d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214847"
---
# <a name="includelib-c"></a>includelib (C++)

生成された .idl ファイルに .idl ファイルまたは .h ファイルを含めます。

## <a name="syntax"></a>構文

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>パラメーター

*.idl という名前*<br/>
生成された .idl ファイルの一部として含める .idl ファイルの名前。

## <a name="remarks"></a>解説

この**includelib** C++属性を指定すると、.idl ファイルまたは .h ファイルが、`importlib` ステートメントの後に生成される .idl ファイルに追加されます。

## <a name="example"></a>例

.Cpp ファイルには、次のコードが表示されます。

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|はい|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)
