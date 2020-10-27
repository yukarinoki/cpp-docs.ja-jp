---
title: C キーワード
description: 標準の C および Microsoft C コンパイラ拡張機能のキーワード。
ms.date: 10/15/2020
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
ms.openlocfilehash: 24981c8d70cb56b4578fd905a30ccc57eaa83d45
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176232"
---
# <a name="c-keywords"></a>C キーワード

" *キーワード* " は、C コンパイラに対して特別な意味を持つ単語です。 変換フェーズ 7 および 8 では、識別子は、C キーワードと同じスペル (大文字と小文字を区別する) にすることはできません。 詳細については、 *プリプロセッサ リファレンス* の「 [変換フェーズ](../preprocessor/phases-of-translation.md)」を参照してください。 識別子の詳細については、[識別子](../c-language/c-identifiers.md)に関するページを参照してください。

## <a name="standard-c-keywords"></a>標準の C キーワード

C 言語では、次のキーワードを使用します。

:::row:::
    :::column:::
        **`auto`**\
        **`break`**\
        **`case`**\
        **`char`**\
        **`const`**\
        **`continue`**\
        **`default`**\
        **`do`**\
        **`double`**\
        **`else`**\
        **`enum`**
    :::column-end:::
    :::column:::
        **`extern`**\
        **`float`**\
        **`for`**\
        **`goto`**\
        **`if`**\
        **`inline`** <sup>1, a</sup>\
        **`int`**\
        **`long`**\
        **`register`**\
        **`restrict`** <sup>1, a</sup>\
        **`return`**
    :::column-end:::
    :::column:::
        **`short`**\
        **`signed`**\
        **`sizeof`**\
        **`static`**\
        **`struct`**\
        **`switch`**\
        **`typedef`**\
        **`union`**\
        **`unsigned`**\
        **`void`**\
        **`volatile`**
    :::column-end:::
    :::column:::
        **`while`**\
        **`_Alignas`** <sup>2, a</sup>\
        **`_Alignof`** <sup>2, a</sup>\
        **`_Atomic`** <sup>2, b</sup>\
        **`_Bool`** <sup>1, a</sup>\
        **`_Complex`** <sup>1, b</sup>\
        **`_Generic`** <sup>2, a</sup>\
        **`_Imaginary`** <sup>1, b</sup>\
        **`_Noreturn`** <sup>2, a</sup>\
        **`_Static_assert`** <sup>2, a</sup>\
        **`_Thread_local`** <sup>2, b</sup>
    :::column-end:::
:::row-end:::

<sup>1</sup> ISO C99 で導入されたキーワード。

<sup>2</sup> ISO C11 で導入されたキーワード。

<sup>a</sup> Visual Studio 2019 バージョン 16.8 以降、これらのキーワードは、 **`/std:c11`** または **`/std:c17`** コンパイラ オプションが指定される場合、C としてコンパイルされるコードでサポートされます。

<sup>b</sup> Visual Studio 2019 バージョン 16.8 以降、これらのキーワードは認識されますが、 **`/std:c11`** または **`/std:c17`** コンパイラ オプションが指定される場合、C としてコンパイルされるコードでは、コンパイラによってサポートされません。

キーワードを再定義することはできません。 ただし、C [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)を使用すると、コンパイルの前にキーワードを置換するテキストを指定できます。

## <a name="microsoft-specific-c-keywords"></a>Microsoft 固有の C キーワード

ANSI C および ISO C 規格では、先頭にアンダースコアが 2 つ付いた識別子がコンパイラ実装用に予約されています。 Microsoft の規則により、Microsoft 固有のキーワード名には先頭にアンダースコアを 2 つ付けることになっています。 これらの単語を識別子名として使用することはできません。 二重アンダースコアの使用など、識別子の名前付けに関する規則については、[識別子](../c-language/c-identifiers.md)に関するページを参照してください。

次のキーワードと特殊な識別子は、Microsoft C コンパイラで認識されます。

:::row:::
    :::column:::
        **`__asm`** <sup>5</sup>\
        **`dllimport`** <sup>4</sup>\
        **`__int8`** <sup>5</sup>\
        **`naked`** <sup>4</sup>\
        **`__based`** <sup>3, 5</sup>
    :::column-end:::
    :::column:::
        **`__except`** <sup>5</sup>\
        **`__int16`** <sup>5</sup>\
        **`__stdcall`** <sup>5</sup>\
        **`__cdecl`** <sup>5</sup>\
        **`__fastcall`**
    :::column-end:::
    :::column:::
        **`__int32`** <sup>5</sup>\
        **`thread`** <sup>4</sup>\
        **`__declspec`** <sup>5</sup>\
        **`__finally`** <sup>5</sup>\
        **`__int64`** <sup>5</sup>
    :::column-end:::
    :::column:::
        **`__try`** <sup>5</sup>\
        **`dllexport`** <sup>4</sup>\
        **`__inline`** <sup>5</sup>\
        **`__leave`** <sup>5</sup>\
        **`static_assert`** <sup>6</sup>
    :::column-end:::
:::row-end:::

<sup>3</sup> **`__based`** キーワードには、32 ビットおよび 64 ビット ターゲット コンパイルに関する使用制限があります。

<sup>4</sup> これらは、 **`__declspec`** で使用するときは特殊な識別子です。他のコンテキストでの使用は制限されません。

<sup>5</sup> 以前のバージョンとの互換性のため、これらのキーワードは先頭に 2 つのアンダースコアが付いているものだけでなく、Microsoft の拡張機能を有効にしている場合は 1 つのアンダースコアが付いているものも使用できます。

<sup>6</sup> <assert.h> を含めない場合、Microsoft Visual C コンパイラによって **`static_assert`** が C11 **`_Static_assert`** キーワードにマッピングされます。

Microsoft 拡張機能は既定で有効になっています。 移植可能なコードの作成を支援するために、コンパイル時に [/Za \(言語拡張機能の無効化)](../build/reference/za-ze-disable-language-extensions.md) オプションを指定することで、Microsoft 拡張機能を無効にできます。 このオプションを使用すると、Microsoft 固有のキーワードの一部が無効になります。

Microsoft 拡張機能を有効にするときは、先に示したキーワードをプログラム内で使用できます。 標準に準拠するために、これらのキーワードのほとんどは二重アンダースコアで始まります。 4 つの例外 ( **`dllexport`** 、 **`dllimport`** 、 **`naked`** 、 **`thread`** ) は、 **`__declspec`** でのみ使用され、先頭の二重アンダースコアは必要ありません。 残りのキーワードについては、下位互換性のために、アンダースコア 1 文字のバージョンがサポートされます。

## <a name="see-also"></a>関連項目

[C の要素](../c-language/elements-of-c.md)
