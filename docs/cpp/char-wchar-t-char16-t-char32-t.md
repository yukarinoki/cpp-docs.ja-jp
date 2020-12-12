---
description: '詳細については、次を参照してください: char、wchar_t、char16_t、char32_t'
title: char、wchar_t、char16_t、char32_t
ms.date: 02/14/2018
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
ms.openlocfilehash: f8bab56bf8a2cebe8409c9dc4ceecf931ec83260
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278793"
---
# <a name="char-wchar_t-char16_t-char32_t"></a>char、wchar_t、char16_t、char32_t

、、 **`char`** **`wchar_t`** および型 **`char16_t`** は、 **`char32_t`** 英数字以外のグリフおよび非印刷文字を表す、英数字を表す組み込み型です。

## <a name="syntax"></a>構文

```cpp
char     ch1{ 'a' };  // or { u8'a' }
wchar_t  ch2{ L'a' };
char16_t ch3{ u'a' };
char32_t ch4{ U'a' };
```

## <a name="remarks"></a>解説

この **`char`** 型は、C および C++ の元の文字型でした。 この型は、 **`unsigned char`** C++ の組み込み型ではない *バイト* を表すためによく使用されます。 この型を使用して、 **`char`** ASCII 文字セットまたは ISO-8859 文字セットの文字、および、シフト JIS や Unicode 文字セットの utf-8 エンコードなどのマルチバイト文字の個々のバイトを格納できます。 型の文字列 **`char`** は、複数バイト文字をエンコードするために使用される場合でも、 *ナロー* 文字列と呼ばれます。 Microsoft コンパイラでは、 **`char`** は8ビット型です。

**`wchar_t`** 型は、実装定義のワイド文字型です。 Microsoft コンパイラでは、Windows オペレーティングシステムのネイティブ文字型である UTF 16LE としてエンコードされた Unicode を格納するために使用される16ビットワイド文字を表します。 汎用 C ランタイム (UCRT) ライブラリ関数のワイド文字バージョンでは、 **`wchar_t`** ネイティブ WINDOWS API のワイド文字バージョンと同様に、パラメーターと戻り値として、およびそのポインターと配列型を使用します。

**`char16_t`** 型と **`char32_t`** 型はそれぞれ16ビットと32ビットのワイド文字を表します。 UTF-16 としてエンコードされた unicode は、型に格納でき **`char16_t`** ます。また、32 utf-8 としてエンコードされた unicode は、型に格納でき **`char32_t`** ます。 これらの型の文字列と **`wchar_t`** はすべて *ワイド* 文字列と呼ばれますが、用語は特に型の文字列を参照し **`wchar_t`** ます。

C++ 標準ライブラリで `basic_string` は、型はナローとワイドの両方の文字列に対して特殊化されています。 文字の型がである場合、文字の型がである場合、文字が型である場合、および文字が型である場合は、を使用し `std::string` **`char`** `std::u16string` **`char16_t`** `std::u32string` **`char32_t`** `std::wstring` **`wchar_t`** ます。 テキストを表すその他の型 (やなど) `std::stringstream` `std::cout` は、ナロー文字列とワイド文字列用に特殊化されています。
