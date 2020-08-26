---
title: import (C++ COM 属性)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: 6b146bdad7d870b534c371a4396993202cc83a4b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842313"
---
# <a name="import"></a>import

メイン IDL から参照する定義が含まれている別の .idl、odl、またはヘッダーファイルを指定します。

## <a name="syntax"></a>構文

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>パラメーター

*idl_file*<br/>
現在のプロジェクトのタイプライブラリにインポートする .idl ファイルの名前です。

## <a name="remarks"></a>解説

**Import** C++ 属性により、 `#import` ステートメントが生成された `import "docobj.idl"` .idl ファイル内のステートメントの下に配置されます。 **Import**属性には、 [import](/windows/win32/Midl/import) MIDL 属性と同じ機能があります。

**Import**属性は、指定されたファイルを、プロジェクトによって生成される .idl ファイルにのみ配置します。**import**属性を使用しても、プロジェクト内のソースコードから指定されたファイル内の構造体を呼び出すことはできません。  プロジェクト内のソースコードから指定されたファイルの構造体を呼び出すには、 [#import](../../preprocessor/hash-import-directive-cpp.md) と属性を使用するか、 `embedded_idl` .h ファイルが存在する場合は *idl_file*の .h ファイルを含めることができます。

## <a name="example"></a>例

コード例を次に示します。

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

生成された .idl ファイル内に次のコードを生成します。

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
```

## <a name="requirements"></a>必要条件

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
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[用意](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
