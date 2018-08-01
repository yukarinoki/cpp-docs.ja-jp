---
title: char、wchar_t、char16_t、char32_t |Microsoft Docs
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
ms.openlocfilehash: 2d0c89df02c624d96c613f6241c9beefd466827e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402615"
---
# <a name="char-wchart-char16t-char32t"></a>char、wchar_t、char16_t、char32_t
種類**char**、 **wchar_t**、 **char16_t**と**char32_t**は文字の英数字を表す組み込み型だけでなく英数字以外のグリフと印刷されない文字。

## <a name="syntax"></a>構文

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>Remarks

**Char** C および C++ で元の文字型します。 型**unsigned char**表すために使用されて多くの場合、*バイト*、これは C++ では組み込み型ではありません。 **Char**文字、ASCII 文字セットや、ISO 8859 文字セットのいずれか Shift JIS などのマルチバイト文字の各バイトまたは Unicode 文字セットの utf-8 エンコーディングを格納する型を使用できます。 文字列の**char**型と呼びます*を絞り込む*マルチ バイト文字のエンコードに使用する場合でも、文字列します。 Microsoft コンパイラで**char**は、8 ビット型です。

**Wchar_t**型は、ワイド文字の実装定義型です。 Microsoft コンパイラでするのに対して、UTF 16LE としてエンコードされた Unicode の格納に使用する 16 ビットのワイド文字を表す Windows オペレーティング システムでネイティブ文字の種類。 ユニバーサル C ランタイム (UCRT) ライブラリの関数の使用方法のワイド文字バージョン**wchar_t**し、そのポインターと配列の型パラメーターと戻り値としては、ネイティブ Windows API のワイド文字バージョンです。

**Char16_t**と**char32_t**型はそれぞれ 16 ビットおよび 32 ビットのワイド文字を表します。 Unicode utf-16 に格納できるようにエンコード、 **char16_t**型、および Unicode utf-32 に格納できるようにエンコード、 **char32_t**型。 これらの型の文字列と**wchar_t**はすべて呼ば*ワイド*多くの場合とは具体的には文字列の場合は、文字列**wchar_t**型。

C++ 標準ライブラリで、`basic_string`ナローとワイドの両方の文字列の型が特殊化します。 使用`std::string`型の文字が場合**char**、`std::u16string`型の文字が場合**char16_t**、`std::u32string`型の文字が場合**char32_t**、および`std::wstring`型の文字が場合**wchar_t**します。 その他のテキストを表す型を含む`std::stringstream`と`std::cout`ナローとワイド文字列の特殊化があります。  