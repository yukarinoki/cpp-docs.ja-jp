---
title: (C++ COM 属性) を含める
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: d9c68601bea4cecd92b371dada5fb086aeb7657f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033698"
---
# <a name="include-c"></a>include (C++)

生成された .idl ファイルに含まれる 1 つまたは複数のヘッダー ファイルを指定します。

## <a name="syntax"></a>構文

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>パラメーター

*header_file*<br/>
生成された .idl ファイルに含まれるファイルの名前。

## <a name="remarks"></a>Remarks

**含める**C++ 属性によって、`#include`ステートメントの下に配置されます、`import "docobj.idl"`生成された .idl ファイル内のステートメント。

**含める**C++ 属性と同じ機能を持つ、[含める](/windows/desktop/Midl/include)MIDL 属性。

## <a name="example"></a>例

次のコードを使用する方法の例を示します**含める**します。 この例では、ファイル include.h のみを含む、`#include`ステートメント。

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)