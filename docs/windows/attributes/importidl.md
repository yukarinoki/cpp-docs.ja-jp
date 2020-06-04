---
title: ///(C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 6e41a98bef079c92b6df6e7eff203301aa9ceae4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166823"
---
# <a name="importidl"></a>importidl

生成された .idl ファイルに、指定した .idl ファイルを挿入します。

## <a name="syntax"></a>構文

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>パラメーター

*idl_file*<br/>
アプリケーションに対して生成される .idl ファイルとマージする .idl ファイルの名前を指定します。

## <a name="remarks"></a>解説

C++この**属性を使用すると**、ライブラリブロックの外側 ( *idl_file*) のセクションが、プログラムによって生成された .idl ファイルのライブラリセクションに、プログラムによって生成される .idl ファイルとライブラリセクション ( *idl_file*) に格納されます。

たとえば、生成された .idl ファイルでハンドコードされた .idl ファイルを使用する場合は **、使用する**ことができます。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
