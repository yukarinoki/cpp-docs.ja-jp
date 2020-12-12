---
description: '詳細情報: インクルード (C++)'
title: インクルード (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 9a7565a931a865b69f0da95da9e92481b27de3b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321351"
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

**インクルード** された C++ 属性により、.idl ファイルまたは .h ファイルが、ステートメントの後に生成される .idl ファイルに追加されます。 `importlib`

## <a name="example"></a>例

.Cpp ファイルには、次のコードが表示されます。

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|はい|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[用意](include-cpp.md)<br/>
[importlib](importlib.md)
