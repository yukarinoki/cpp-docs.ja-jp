---
title: C キーワード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80c1f0d4ac5d843732771281202612e31a4073c2
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860889"
---
# <a name="c-keywords"></a>C キーワード

"キーワード" は、C コンパイラに対して特別な意味を持つ単語です。 変換フェーズ 7 および 8 では、識別子は、C キーワードと同じスペル (大文字と小文字を区別する) にすることはできません  (『*プリプロセッサ リファレンス*』の「[変換の段階](../preprocessor/phases-of-translation.md)」の説明を参照してください。識別子の詳細については、「[識別子](../c-language/c-identifiers.md)」を参照してください。)C 言語では、次のキーワードを使用します。

|||||
|-|-|-|-|
|**auto**|**double**|**int**|**struct**|
|**break**|**else**|**long**|**switch**|
|**case**|**enum**|**register**|**typedef**|
|**char**|**extern**|**return**|**union**|
|**const**|**float**|**short**|**unsigned**|
|**continue**|**for**|**signed**|**void**|
|**default**|**goto**|**sizeof**|**volatile**|
|**do**|**if**|**static**|**while**|

キーワードは再定義できません。 ただし、C [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)を使用してコンパイルする前にキーワードと置き換えるテキストを指定できます。

**Microsoft 固有の仕様**

ANSI C 規格では、先頭にアンダースコアを 2 つ持つ識別子はコンパイラ実装用に予約されています。 そこで、Microsoft の規約では、Microsoft 固有のキーワード名には先頭にアンダースコアを 2 つ付けることになっています。 したがって、これらの単語を識別子名として使用することはできません。 二重アンダースコアの使用など、識別子の名前付けに関する ANSI の規則については、「[識別子](../c-language/c-identifiers.md)」を参照してください。

次のキーワードと特殊な識別子は、Microsoft C コンパイラで認識されます。

|||||
|-|-|-|-|
|**__asm**|**dllimport**<sup>2</sup>|**__int8**|**naked**<sup>2</sup>|
|**__based**<sup>1</sup>|**__except**|**__int16**|**__stdcall**|
|**__cdecl**|**__fastcall**|**__int32**|**thread**<sup>2</sup>|
|**__declspec**|**__finally**|**__int64**|**__try**|
|**dllexport**<sup>2</sup>|**__inline**|**__leave**||

<sup>1</sup> **__based** キーワードには、32 ビットおよび 64 ビット ターゲット コンパイルに関する使用制限があります。

<sup>2</sup> これらは、**__declspec** で使用するときは特殊な識別子です。他のコンテキストでの使用は制限されていません。

Microsoft 拡張機能は既定で有効になっています。 完全に移植性のあるプログラムにするには、/Za オプション (ANSI 互換性用にコンパイル) を指定してコンパイル中に Microsoft 拡張機能を無効にできます。 これにより、Microsoft 固有のキーワードが無効になります。

Microsoft 拡張機能を有効にするときは、先に示したキーワードをプログラム内で使用できます。 ANSI 準拠の場合、これらのキーワードのほとんどは二重アンダースコアで始まります。 4 つの例外、**dllexport**、**dllimport**、**naked**、および **thread** は、**__declspec** のみで使用されます。したがって、先頭に二重アンダースコアは必要ありません。 残りのキーワードについては、下位互換性のために、アンダースコア 1 文字のバージョンがサポートされます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[C の要素](../c-language/elements-of-c.md)
