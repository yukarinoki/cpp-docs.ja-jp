---
title: cpp_quote (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 451313b5bd1eb5011f1175de5c3bcfe6fb054299
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214917"
---
# <a name="cpp_quote"></a>cpp_quote

指定された文字列を、引用符ではなく、生成された .idl ファイルに出力します。

## <a name="syntax"></a>構文

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>パラメーター

*statement*<br/>
C 命令。

## <a name="remarks"></a>解説

**Cpp_quote** C++属性は、.idl ファイルにプリプロセッサディレクティブを配置する場合に便利です。

また、 **cpp_quote**を使用し、MIDL コンパイルの一部として .h ファイルを生成することもできます。 たとえば、IDL 属性を使用C++ C++しているが、一部のタスクでこのファイルを使用できないヘッダーファイルがある場合は、それをコンパイルして、MIDL によって生成された .h ファイルを作成できます。このファイルを使用できます。

**Cpp_quote**属性には、 [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Cpp_quote**の使用例については、「[デュアル](dual.md)の例」を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)
