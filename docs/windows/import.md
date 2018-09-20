---
title: インポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9e2ee577c3285a7e4c3db2fb19d934417bbe26d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411561"
---
# <a name="import"></a>import

メイン IDL から参照する定義を含む .idl、.odl ファイル、またはヘッダーのもう 1 つのファイルを指定します。

## <a name="syntax"></a>構文

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>パラメーター

*idl_file*<br/>
現在のプロジェクトのタイプ ライブラリにインポートする .idl ファイルの名前。

## <a name="remarks"></a>Remarks

**インポート**C++ 属性によって、`#import`ステートメントの下に配置される、`import "docobj.idl"`生成された .idl ファイル内のステートメント。 **インポート**属性と同じ機能を持つ、[インポート](/windows/desktop/Midl/import)MIDL 属性。

**インポート**属性は、プロジェクトによって生成される .idl ファイルに指定されたファイルを配置するだけ、**インポート**属性ではソース コードから指定したファイルの構造を呼び出すことはできませんプロジェクト。  プロジェクトのソース コードから、指定したファイルの構造を呼び出すには使用か[#import](../preprocessor/hash-import-directive-cpp.md)と`embedded_idl`または属性の .h ファイルを含めることができます、 *idl_file*.h ファイルが存在する場合は、します。

## <a name="example"></a>例

コード例を次に示します。

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

生成された .idl ファイルに次のコードが生成されます。

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[スタンドアロン属性](../windows/stand-alone-attributes.md)<br/>
[importidl](../windows/importidl.md)<br/>
[importlib](../windows/importlib.md)<br/>
[include](../windows/include-cpp.md)<br/>
[includelib](../windows/includelib-cpp.md)  