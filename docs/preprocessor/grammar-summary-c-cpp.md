---
title: プリプロセッサの文法の概要 (C/C++)
description: Microsoft C/c + + コンパイラ (MSVC) プリプロセッサ文法構文を定義し、説明します。
ms.date: 01/22/2021
helpviewer_keywords:
- grammar
- preprocessor, grammar
ms.openlocfilehash: dbe46a67337bf55cb98100878dedb8c92120472b
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713637"
---
# <a name="preprocessor-grammar-summary-cc"></a>プリプロセッサの文法の概要 (C/C++)

この記事では、C および C++ プリプロセッサの正式な文法について説明します。 プリプロセスディレクティブと演算子の構文について説明します。 詳細については、「[プリプロセッサ](../preprocessor/preprocessor.md)[ディレクティブとプラグマディレクティブ」と「 `__pragma` `_Pragma` キーワードとキーワード](./pragma-directives-and-the-pragma-keyword.md)」を参照してください。

## <a name="definitions-for-the-grammar-summary"></a><a name="definitions"></a> 文法の概要の定義

終端は構文定義内のエンドポイントです。 他の解決はありません。 終端には、予約語およびユーザー定義の識別子が含まれます。

非終端は構文内のプレースホルダーです。 ほとんどは、この構文概要の他の場所で定義されています。 定義は再帰的に行うことができます。 次の非終端要素は、 *C++ 言語リファレンス* の [構文規則](../cpp/lexical-conventions.md)セクションで定義されています。

*`constant`*, *`constant-expression`*, *`identifier`*, *`keyword`*, *`operator`*, *`punctuator`*

省略可能な構成要素には添字 <sub>opt</sub> を付けます。 たとえば、次の構文は、中かっこで囲まれた省略可能な式を示しています。

**`{`***`expression`*<sub>選択</sub>**`}`**

## <a name="document-conventions"></a><a name="conventions"></a> ドキュメントの表記規則

構文規則では、構文のコンポーネントごとに異なるフォント属性を使用します。 シンボルとフォントは次のとおりです。

| 属性 | 説明 |
|---------------|-----------------|
| *`nonterminal`* | 斜体は、非終端要素を示します。 |
| **`#include`** | 太字で示される終端要素は、示されたとおりに入力する必要があるリテラル予約語およびシンボルです。 このコンテキストの文字は、常に大文字と小文字が区別されます。 |
| <sub>opt</sub> | 後ろに <sub>opt</sub> が続く非終端要素は、常に省略可能です。|
| 既定のタイプフェイス | このタイプフェイスで記述されているか、示されているセット内の文字は、ステートメント内で終端要素として使用できます。 |

非終端要素の後にコロン () を付けると、 **`:`** その定義が導入されます。 代替定義は別の行に示されます。

コード構文ブロックでは、既定のタイプフェイスのこれらのシンボルには特別な意味があります。

| Symbol | 説明 |
|---|---|
| \[ ] | 角かっこは、省略可能な要素を囲みます。 |
| { \| } | 中かっこは、縦棒で区切られた別の要素を囲みます。 |
| ... | 前の要素パターンを繰り返すことができることを示します。 |

コード構文ブロック、コンマ ( `,` )、ピリオド ( `.` )、セミコロン ( `;` )、コロン ( `:` )、かっこ ( `( )` )、二重引用符 ( `"` )、および単一引用符 ( `'` ) はリテラルです。

## <a name="preprocessor-grammar"></a><a name="grammar"></a> プリプロセッサの文法

*`control-line`*:\
&emsp;**`#define`***`identifier`* *`token-string`* <sub>選択</sub>\
&emsp;**`#define`***`identifier`* **`(`** *`identifier`*<sub>選択</sub> **`,`**... **`,`***`identifier`* <sub></sub> **`)`** 選択 *`token-string`*<sub>選択</sub>\
&emsp;**`#include`** **`"`**_`path-spec`_**`"`**\
&emsp;**`#include`** **`<`**_`path-spec`_**`>`**\
&emsp;**`#line`***`digit-sequence`* **`"`**_`filename`_**`"`**<sub>選択</sub>\
&emsp;**`#undef`** *`identifier`*\
&emsp;**`#error`** *`token-string`*\
&emsp;**`#pragma`** *`token-string`*

*`constant-expression`*:\
&emsp;**`defined(`** *`identifier`* **`)`**\
&emsp;**`defined`** *`identifier`*\
&emsp;その他の定数式

*`conditional`*:\
&emsp; *`if-part`* *`elif-parts`* <sub>opt</sub> *`else-part`* <sub>opt</sub> *`endif-line`*

*`if-part`*:\
&emsp;*`if-line`* *`text`*

*`if-line`*:\
&emsp;**`#if`** *`constant-expression`*\
&emsp;**`#ifdef`** *`identifier`*\
&emsp;**`#ifndef`** *`identifier`*

*`elif-parts`*:\
&emsp;*`elif-line`* *`text`*\
&emsp;*`elif-parts`* *`elif-line`* *`text`*

*`elif-line`*:\
&emsp;**`#elif`** *`constant-expression`*

*`else-part`*:\
&emsp;*`else-line`* *`text`*

*`else-line`*:\
&emsp;**`#else`**

*`endif-line`*:\
&emsp;**`#endif`**

*`digit-sequence`*:\
&emsp;*`digit`*\
&emsp;*`digit-sequence`* *`digit`*

*`digit`* : 次のいずれか\
&emsp;**`0` `1` `2` `3` `4` `5` `6` `7` `8` `9`**

*`token-string`*:\
&emsp;文字列 *`token`*

*`token`*:\
&emsp;*`keyword`*\
&emsp;*`identifier`*\
&emsp;*`constant`*\
&emsp;*`operator`*\
&emsp;*`punctuator`*

*`filename`*:\
&emsp;有効なオペレーティング システム ファイル名

*`path-spec`*:\
&emsp;有効なファイル パス

*`text`*:\
&emsp;テキストの任意のシーケンス

> [!NOTE]
> 「」、「」、「」、「」、「」、「」、「」、「」、「」、「」、「」、「」、「 *」、「*」、 [「」、](../cpp/lexical-conventions.md) *`constant`* *`constant-expression`* *`identifier`* *`keyword`* *`operator`* *`punctuator`*

## <a name="see-also"></a>関連項目

[C/C++ のプリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)
