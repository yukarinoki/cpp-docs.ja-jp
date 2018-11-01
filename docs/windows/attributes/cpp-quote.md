---
title: cpp_quote (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 5a281f9f88412df4d3ee18bff1302b19433e07f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466951"
---
# <a name="cppquote"></a>cpp_quote

生成された .idl ファイルに、引用符なしの指定した文字列を出力します。

## <a name="syntax"></a>構文

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>パラメーター

*statement*<br/>
C 命令。

## <a name="remarks"></a>Remarks

**Cpp_quote** C++ 属性は、.idl ファイル内のプリプロセッサ ディレクティブを配置する場合に便利です。

使用することも**cpp_quote** MIDL コンパイルの一部として、.h ファイルを生成します。 たとえば、C の IDL 属性を使用していて、このファイルをいくつかのタスクを使用することはできません、C++ ヘッダー ファイルがある場合は、しをコンパイルできますを使用できる MIDL で生成された .h ファイルを作成すること。

**Cpp_quote**属性と同じ機能を持つ、 [cpp_quote](/windows/desktop/Midl/cpp-quote) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[デュアル](dual.md)例については、使用する方法を使用して、 **cpp_quote**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)