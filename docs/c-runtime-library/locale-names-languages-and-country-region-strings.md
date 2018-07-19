---
title: ロケール名、言語、および国/地域識別文字列 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeaeb21dfabac173b639fe4b3e1518b276c629a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391816"
---
# <a name="locale-names-languages-and-countryregion-strings"></a>ロケール名、言語、および国/地域識別文字列
`setlocale` および `_create_locale` 関数の*ロケール*引数は、Windows NLS API でサポートされているロケール名、言語、国/地域コード、コード ページなどを使用して設定できます。 *ロケール*引数は次の形式になります。  
  
> *locale* :: "*locale_name*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "*language*\[\_*country-region*]\[.*code_page*]]"  
&nbsp;&nbsp;&nbsp;&nbsp;| ".*code_page*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "C"  
&nbsp;&nbsp;&nbsp;&nbsp;| ""  
&nbsp;&nbsp;&nbsp;&nbsp;| NULL  
  
 ロケール名形式が推奨されます。たとえば、英語 (米国) の `en-US`、またはボスニア語 (キリル、ボスニア・ヘルツェゴビナ) の `bs-Cyrl-BA` などです。 ロケール名のセットは「 [ロケール名](http://msdn.microsoft.com/library/windows/desktop/dd373814.aspx)」に記述されています。 Windows オペレーティング システムのバージョンによってサポートされているロケール名の一覧については、「 **各国語サポートの (NLS) の API リファレンス** 」の [Culture Name](https://www.microsoft.com/resources/msdn/goglobal/default.mspx)の列を参照してください。 このリソースは、ロケール名のサポートされている言語、スクリプト、および地域の部分を示しています。 既定以外の並べ替え順序を持つ、サポートされているロケール名については、「 **並べ替え順序の識別子** 」の [Locale name](http://msdn.microsoft.com/library/windows/desktop/dd374060.aspx)の列を参照してください。 Windows オペレーティング システムのバージョンごとの言語および地域のサポートに関する詳細については、[MS-LCID]: Windows Language Code Identifier (LCID) Reference ([MS-LCID]: Windows 言語コード識別子 (LCID) リファレンス) の「[Appendix A: Product Behavior (付録 A: 製品の動作)](http://msdn.microsoft.com/goglobal/bb896001.aspx)」をご覧ください。 Windows 10 以降では、有効な BCP-47 の言語タグに対応するロケール名が許可されています。 たとえば、`jp-US` は有効な BCP-47 タグですが、ロケール機能としては `US` にのみ有効です。  
  
 ロケールを作成するために、言語識別文字列、または言語識別文字列と国/地域識別文字列が使用される場合、 *言語*[*_国_地域*[.*コード_ページ*]] form is stored in the locale setting for a category when a 言語 string, or 言語 string and country/region string, is used to create the locale. サポートされる言語識別文字列のセットは「 [Language Strings](../c-runtime-library/language-strings.md)」、サポートされるすべての国/地域識別文字列のリストは「 [Country/Region Strings](../c-runtime-library/country-region-strings.md)」に記述されています。 指定された言語が、指定された国または地域と関連付けられていない場合、指定された国または地域の既定の言語は、ロケール設定に格納されます。 この形式は、コードに埋め込まれた、またはストレージに対してシリアル化されたロケール文字列にはお勧めしません。これらの文字列は、ロケール名形式よりも、オペレーティング システムの更新によって変更される可能性が高いからです。  
  
 コード ページは、ロケールに関連付けられた ANSI/OEM コード ページです。 コード ページは、言語または言語と国/地域のみによってロケールを指定すると決定されます。 特殊な値 `.ACP` は国/地域の ANSI コード ページを指定します。 特殊な値 `.OCP` は国/地域の OEM コード ページを指定します。 たとえば、ロケールとして `"Greek_Greece.ACP"` を指定すると、ロケールは `Greek_Greece.1253` (ギリシャ語の ANSI コード ページ) として格納されます。また、ロケールとして `"Greek_Greece.OCP"` を指定すると、 `Greek_Greece.737` (ギリシャ語の OEM のコード ページ) として格納されます。 コード ページの詳細については、「 [Code Pages](../c-runtime-library/code-pages.md)」を参照してください。 Windows でサポートされているコード ページの一覧については、「 [コード ページの識別子](http://msdn.microsoft.com/library/windows/desktop/dd317756.aspx)」を参照してください。  
  
 ロケールを指定するためにコード ページだけを使用する場合、システムの既定の言語と国または地域が使用されます。 たとえば、英語 (米国) に構成されたシステムのロケールとして `".1254"` (ANSI トルコ語) を指定した場合は、格納されているロケールは `English_United States.1254`です。 この形式はお勧めしません。これにより一貫性のない動作が実行される可能性があるためです。  
  
`C` の*ロケール*引数値は、C 翻訳のための ANSI に準拠した最小環境を指定します。 `C` ロケールは、任意の `char` データ型が 1 バイトであり、値は常に 256 未満であると推定します。 *ロケール*が空の文字列をポイントしている場合は、実装定義のネイティブ環境になります。  
  
`setlocale` 関数と `_wsetlocale` 関数に `LC_ALL` カテゴリを使用して、ロケールのカテゴリのすべてを同時に指定できます。 カテゴリはすべて同じロケールに設定できますが、次の形式を持つロケール引数を使用して各カテゴリを個別に設定できます。  
  
> LC_ALL_specifier :: locale  
&nbsp;&nbsp;&nbsp;&nbsp;| [LC_COLLATE=locale][;LC_CTYPE=locale][;LC_MONETARY=locale][;LC_NUMERIC=locale][;LC_TIME=locale]  
  
セミコロンで区切って複数のカテゴリの種類を指定できます。 指定されていないカテゴリの種類は、現在のロケール設定を使用します。 たとえば、このコード スニペットは、すべてのカテゴリの現在のロケールを `de-DE` に設定し、カテゴリ `LC_MONETARY` を `en-GB` に、カテゴリ `LC_TIME` を `es-ES` に設定します。  
  
```C  
_wsetlocale(LC_ALL, L"de-DE");  
_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");  
```  
  
## <a name="see-also"></a>参照  
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)   
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [言語識別文字列](../c-runtime-library/language-strings.md)   
 [国/地域別文字列](../c-runtime-library/country-region-strings.md)