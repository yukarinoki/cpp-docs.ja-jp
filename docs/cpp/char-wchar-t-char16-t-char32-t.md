---
title: char、wchar_t、char16_t、char32_t |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs:
- C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dc38eb9742459139747578a8227bdfaee8bb8a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413896"
---
# <a name="char-wchart-char16t-char32t"></a>char、wchar_t、char16_t、char32_t
種類**char**、 **wchar_t**、 **char16_t**と**char32_t**が英数字文字を表す組み込み型と同様英数字以外のグリフと印刷されない文字。

## <a name="syntax"></a>構文

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>コメント

**Char**型は C および C++ での元の文字型でした。 型**unsigned char**表すために多くの場合、使用、*バイト*、これは C++ では組み込み型ではありません。 **Char** ASCII 文字セットまたは ISO 8859 文字セットのいずれかとから Shift JIS などのマルチバイト文字の各バイトまたは Unicode 文字セットの utf-8 エンコード文字を格納する型を使用することができます。 文字列の**char**型と呼びます*を絞り込む*マルチ バイト文字のエンコードに使用する場合でも、文字列です。 Microsoft コンパイラで**char**は 8 ビット型です。

**Wchar_t**型は、実装定義のワイド文字型。 Microsoft コンパイラで UTF 16LE としてエンコードされた Unicode の格納に使用する 16 ビットのワイド文字を表す、Windows オペレーティング システムでネイティブの文字型。 Universal C Runtime (UCRT) ライブラリの関数の使用方法のワイド文字バージョン**wchar_t**とそのポインターと配列の種類パラメーターと戻り値は、としては、ネイティブの Windows API のワイド文字バージョンです。

**Char16_t**と**char32_t**の種類が 16 ビットおよび 32 ビットのワイド文字をそれぞれ表します。 格納できる utf-16 としてエンコードされた Unicode、 **char16_t**型、および utf-32 に格納できるようにエンコードされた Unicode、 **char32_t**型です。 これらの型の文字列と**wchar_t**はすべて呼ば*ワイド*多くの場合とは具体的には文字列の場合は、文字列**wchar_t**型です。

C++ 標準ライブラリで、`basic_string`型はナローとワイド文字の両方の特殊化です。 使用して`std::string`型の文字が場合**char**、`std::u16string`型の文字が場合**char16_t**、`std::u32string`型の文字が場合**char32_t**、および`std::wstring`型の文字が場合**wchar_t**です。 テキストを表すその他の型を含む`std::stringstream`と`std::cout`ナロー文字列とワイド文字列向けに特殊化があります。  
  
