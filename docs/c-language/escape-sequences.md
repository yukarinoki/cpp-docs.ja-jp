---
title: エスケープ シーケンス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- "\r escape sequence"
- double backslash
- horizontal-tab 	 escape sequence
- (') single quotation mark
- "bell character \a escape sequence"
- escape sequences
- hexadecimal escape sequence
- carriage returns
- tab 	 escape sequence
- "\f escape sequence"
- quotation marks, single
- "formfeed \f escape sequence"
- "\v escape sequence"
- control character escape sequences
- " symbol in escape sequences"
- octal escape sequence
- escape characters
- "newline character \n escape sequence"
- nongraphic control characters
- question mark, literal
- "\nescape sequence"
- "vertical tab \v escape sequence"
- "\a escape sequence"
- '? symbol'
- '? symbol, escape sequence character'
- "	 escape sequence"
- backspace escape sequence
ms.assetid: 5aef377f-a76c-4d5c-aa04-8308758ad6a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd58f7418e2e6a2ca7592c345c5d71729cf8324
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32388829"
---
# <a name="escape-sequences"></a>エスケープ シーケンス
先頭に円記号 (**\\**) が指定されている、アルファベットや数字で構成される文字の組み合わせは、"エスケープ シーケンス" と呼ばれます。 改行文字や単一引用符など、文字定数内の特定の文字を表すには、エスケープ シーケンスを使用する必要があります。 エスケープ シーケンスは 1 つの文字と見なされるため、文字定数として有効です。  
  
 通常、エスケープ シーケンスは、ターミナルとプリンターでは、復帰とタブ移動などの操作を指定するために使用されます。 これらは、印字できない文字と、二重引用符 (**"**) などの通常は特別な意味を持つ文字のリテラル表現を提供するためにも使用されます。 次の表は、ANSI エスケープ シーケンスと、それが何を表すかを示す一覧です。  
  
 文字シーケンスがトライグラフとして誤って解釈されるような場合、疑問符の前に円記号 (**\\?**) を置くと、リテラル疑問符を指定できます。 詳細については、「[トライグラフ](../c-language/trigraphs.md)」を参照してください。  
  
### <a name="escape-sequences"></a>エスケープ シーケンス  
  
|エスケープ シーケンス|表現|  
|---------------------|----------------|  
|**\a**|ベル (警告)|  
|**\b**|バックスペース|  
|**\f**|フォーム フィード|  
|**\n**|改行|  
|**\r**|キャリッジ リターン|  
|**\t**|水平タブ|  
|**\v**|垂直タブ|  
|**\\'**|単一引用符|  
|**\\"**|二重引用符|  
|**\\\\**|円記号|  
|**\\?**|リテラル疑問符|  
|**\\** *ooo*|8 進表記の ASCII 文字|  
|**\x** *hh*|16 進表記の ASCII 文字|  
|**\x** *hhhh*|このエスケープ シーケンスがワイド文字定数または Unicode 文字列リテラルで使用されている場合は、16 進表記の Unicode 文字。<br /><br /> たとえば、`WCHAR f = L'\x4e00'` または `WCHAR b[] = L"The Chinese character for one is \x4e00"` のようにします。|  
  
 **Microsoft 固有の仕様**  
  
 表に示されていない文字の前に円記号が指定されていると、コンパイラは未定義の文字を文字そのものとして処理します。 たとえば、`\c` は `c` として処理されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
 エスケープ シーケンスは、ディスプレイ デバイスに非グラフィカル制御文字を渡すことができます。 たとえば、ESC 文字 (**\033**) は、端末またはプリンターの制御コマンドの最初の文字としてよく使用されます。 一部のエスケープ シーケンスはデバイス固有です。 たとえば、垂直タブとフォーム フィードのエスケープ シーケンス (**\v** と **\f**) は、画面出力には影響しませんが、適切なプリンター操作を実行します。  
  
 また、円記号 (**\\**) を連結文字としても使用できます。 円記号のすぐ後に改行文字 (Enter キーを押すことに相当します) があると、コンパイラは円記号と改行文字を無視し、前の行の一部として次の行を処理します。 これは、主に、1 行より長いプリプロセッサ定義で便利です。 例:  
  
```  
#define assert(exp) \  
( (exp) ? (void) 0:_assert( #exp, __FILE__, __LINE__ ) )  
```  
  
## <a name="see-also"></a>参照  
 [C 文字定数](../c-language/c-character-constants.md)