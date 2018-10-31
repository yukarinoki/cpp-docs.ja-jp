---
title: (C++ COM 属性) を含める |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.include
dev_langs:
- C++
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14a58573af8b8cb917d7aaaa864b6b4d61e70172
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063004"
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