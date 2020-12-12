---
description: '詳細情報: export'
title: export (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 40c802f906d62d72be2c3126159b089c4d24d5b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236296"
---
# <a name="export"></a>エクスポート

データ構造を .idl ファイルに配置します。

## <a name="syntax"></a>構文

```cpp
[export]
```

## <a name="remarks"></a>解説

C++ 属性を使用する **`[export]`** と、データ構造が .idl ファイルに配置され、任意の言語で使用できるようにするバイナリ互換形式で、タイプライブラリで使用できるようになります。

**`[export]`** クラスにパブリックメンバーのみが含まれている場合でも、クラスに属性を適用することはできません (と同等 **`struct`** )。

名前 **`enum`** のないまたはをエクスポートすると **`struct`** 、 **__unnamed**<em>x</em>で始まる名前が付けられます。ここで、 *x* は連番です。

エクスポートに有効な typedef は、基本型、構造体、共用体、列挙型、または型識別子です。  詳細については、「」を参照してください [`typedef`](/windows/win32/Midl/typedef) 。

## <a name="example"></a>例

次のコードは、属性の使用方法を示してい **`[export]`** ます。

```cpp
// cpp_attr_ref_export.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`union`**、 **`typedef`** 、 **`enum`** 、 **`struct`** 、または **`interface`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)
