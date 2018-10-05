---
title: idl_quote (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_quote
dev_langs:
- C++
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f4050e78e6313b77808c1a1ed790e2b7082122d
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791126"
---
# <a name="idlquote"></a>idl_quote

Visual C の現在のバージョンでサポートされていない IDL コンストラクトを使用することができ、生成された .idl ファイルに渡すことがあります。

## <a name="syntax"></a>構文

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>パラメーター

*テキスト*<br/>
コンパイラ エラーを返さずに生成された .idl ファイルに渡す Visual C コンパイラが意図されている属性名。

## <a name="remarks"></a>Remarks

場合、 **idl_quote** C++ 属性は、(セミコロン、右かっこの後)、スタンドアロン属性として使用*テキスト*は、マージされた .idl ファイルに配置されます。 場合**idl_quote**シンボルで使用されて*テキスト*シンボルに対する属性ブロック内に配置されます。

## <a name="example"></a>例

次のコードは、サポートされていない属性を指定する方法を示します (を使用して**で**、サポートされる) と定義して、未定義の .idl コンストラクトを使用する方法。

```cpp
// cpp_attr_ref_idl_quote.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];

[export]
struct MYFLOT {
   int i;
};

[export]
struct MYDUB {
   int i;
};

[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];

typedef struct _S1_TYPE {
   long l1;

union {
   MYFLOT f1; MYDUB d2; } U1_TYPE;
} S1_TYPE;

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]
__interface IStatic{
   HRESULT Func1([idl_quote("in")] int i);
   HRESULT func( S1_TYPE* myStruct );
};
```

このコードにより、`MYFLOT`と`MYDUB`と*テキスト*エントリが生成された .idl ファイルに配置されます。 *名前*パラメーターを使い*テキスト*を参照する前に配置する*名前*で生成された .idl ファイル。 *依存関係*パラメーターを強制的にする前に配置する依存関係のリスト定義*テキスト*で生成された .idl ファイル。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)  