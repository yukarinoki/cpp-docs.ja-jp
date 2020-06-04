---
title: import (C++ COM 属性)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: f2a0aa9a68c081e83a7a5278aa37a7fddac85416
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166837"
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

**Import** C++属性を指定すると、生成された .idl ファイルの `import "docobj.idl"` ステートメントの下に `#import` ステートメントが配置されます。 **Import**属性には、 [import](/windows/win32/Midl/import) MIDL 属性と同じ機能があります。

**Import**属性は、指定されたファイルを、プロジェクトによって生成される .idl ファイルにのみ配置します。**import**属性を使用しても、プロジェクト内のソースコードから指定されたファイル内の構造体を呼び出すことはできません。  プロジェクトのソースコードから指定されたファイルの構造体を呼び出すには、 [#import](../../preprocessor/hash-import-directive-cpp.md)と `embedded_idl` 属性を使用するか、.h ファイルが存在する場合は*idl_file*の .h ファイルを含めることができます。

## <a name="example"></a>例

次のコードは、次の処理を実行します。

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

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
