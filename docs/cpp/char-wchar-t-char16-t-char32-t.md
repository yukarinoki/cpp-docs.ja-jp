---
title: char、wchar_t、char16_t、char32_t
ms.date: 02/14/2018
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
ms.openlocfilehash: 8d109ec452df33b774848229837ed3e2eae80dc4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181019"
---
# <a name="char-wchar_t-char16_t-char32_t"></a>char、wchar_t、char16_t、char32_t

**Char**、 **wchar_t**、 **char16_t** **char32_t**型は、英数字以外のグリフと非印刷文字を表す、英数字を表す組み込み型です。

## <a name="syntax"></a>構文

```cpp
char     ch1{ 'a' };  // or { u8'a' }
wchar_t  ch2{ L'a' };
char16_t ch3{ u'a' };
char32_t ch4{ U'a' };
```

## <a name="remarks"></a>解説

**Char**型は、C およびC++の元の文字型でした。 **Unsigned char**型は、のC++組み込み型ではない*バイト*を表すためによく使用されます。 **Char**型を使用して、ASCII 文字セットの文字、または ISO-8859 文字セットの文字を格納できます。また、シフト JIS や Unicode 文字セットの utf-8 エンコードなど、マルチバイト文字の個々のバイトを格納することもできます。 **Char**型の文字列は、マルチバイト文字をエンコードするために使用される場合でも、*ナロー*文字列と呼ばれます。 Microsoft コンパイラでは、 **char**は8ビット型です。

**Wchar_t**型は、実装定義のワイド文字型です。 Microsoft コンパイラでは、Windows オペレーティングシステムのネイティブ文字型である UTF 16LE としてエンコードされた Unicode を格納するために使用される16ビットワイド文字を表します。 ワイド文字バージョンのユニバーサル C ランタイム (UCRT) ライブラリ関数は、ネイティブ Windows API のワイド文字バージョンと同様に、 **wchar_t**とそのポインター型および配列型をパラメーターと戻り値として使用します。

**Char16_t**型と**char32_t**型はそれぞれ16ビットと32ビットのワイド文字を表します。 UTF-16 としてエンコードされた unicode は**char16_t**型に格納でき、32 utf-8 としてエンコードされた unicode は**char32_t**型に格納できます。 これらの型および**wchar_t**の文字列はすべて*ワイド*文字列として参照されますが、用語は特に**wchar_t**型の文字列を参照します。

C++標準ライブラリでは、`basic_string` 型はナローとワイドの両方の文字列に特化されています。 文字が**char**型の場合は `std::string` を使用し、文字が**char16_t**型の場合は `std::u16string` **、char32_t 型**の場合は `std::u32string`、文字**の型が**`std::wstring` の場合は wchar_t を使用します。 `std::stringstream` や `std::cout` など、テキストを表すその他の型には、ナロー文字列とワイド文字列用の特殊化があります。
