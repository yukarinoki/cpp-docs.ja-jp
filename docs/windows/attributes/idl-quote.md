---
description: '詳細については、次を参照してください: idl_quote'
title: idl_quote (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_quote
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
ms.openlocfilehash: 5aa389214283c188f71190eec41e22d396d887cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275439"
---
# <a name="idl_quote"></a>idl_quote

では、現在のバージョンの Visual C++ でサポートされていない IDL 構造体を使用して、生成された .idl ファイルに渡すことができます。

## <a name="syntax"></a>構文

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>パラメーター

*text*<br/>
コンパイラエラーを返さずに、生成された .idl ファイルに渡す Microsoft C++ コンパイラの属性名。

## <a name="remarks"></a>解説

**Idl_quote** C++ 属性がスタンドアロン属性として使用されている場合 (右角かっこの後にセミコロンが付いている場合)、*テキスト* はそのままマージされた .idl ファイルに配置されます。 シンボルに対して **idl_quote** が使用されている場合、 *テキスト* はそのシンボルの属性ブロック内に配置されます。

## <a name="example"></a>例

次のコードは、サポートされていない属性を指定する方法を示しています ( **で** はを使用します)。また、undefined コンストラクトを定義して使用する方法を示します。

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

このコードにより `MYFLOT` 、および `MYDUB` という *テキスト* エントリが生成された .idl ファイルに配置されます。 *Name* パラメーターは、生成された .idl ファイル内の *名前* を参照するすべてのものより前に *テキスト* を強制的に配置します。 *Dependencies* パラメーターを指定すると、生成された .idl ファイル内の *テキスト* の前に依存関係リストの定義が強制的に配置されます。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)
