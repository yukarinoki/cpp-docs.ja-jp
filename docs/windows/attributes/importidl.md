---
description: 詳細については、「」を参照してください。
title: ///(C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: b10caa9f4b1467727c70b6d968ca6aa33b58da0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329884"
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

インポート **tidl** C++ 属性は、ライブラリブロックの外側のセクション ( *idl_file*) をプログラムによって生成された .idl ファイルに、ライブラリセクション ( *idl_file*) をプログラムの生成された .idl ファイルのライブラリセクションに配置します。

たとえば、生成された .idl ファイルでハンドコードされた .idl ファイルを使用する場合は **、使用する** ことができます。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[用意](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
