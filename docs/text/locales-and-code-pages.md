---
title: ロケールとコード ページ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], about locales
- locale IDs [C++]
- locales [C++]
- code pages [C++]
- code pages [C++], dynamically changing
- character sets [C++], code pages
- multibyte code pages [C++]
- character sets [C++], locales
- localization [C++], code pages
- localization [C++], locales
- code pages [C++], locales
- conventions [C++], international character support
ms.assetid: bd937361-b6d3-4c98-af95-beb7c903187b
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7dd3c5356df7b80f21605e325158e87cc5a71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="locales-and-code-pages"></a>ロケールとコード ページ
ロケール ID は、特定の地域の規則や言語を反映します。 1 つの言語が複数の国や地域で使用されることもあります。たとえば、ポルトガル語は、ポルトガルだけでなくブラジルでも使用されています。 逆に、1 つの国や地域に複数の公用語が存在する場合もあります。 たとえば、カナダでは、公用語として英語とフランス語の 2 つの言語が使用されています。 そこでカナダには、カナダ英語とカナダ フランス語の 2 つの異なったロケールが存在します。 ロケールに依存するカテゴリとしては、日付の形式や通貨値の表示形式などがあります。  
  
 テキストやデータの書式は言語で決まりますが、地元の約束事は国や地域単位で決定されます。 言語にはそれぞれ、コード ページで表される固有のマッピングが設定され、区切り記号や数字などのアルファベット以外の文字も含まれています。 コード ページとは文字セットのことであり、その地域の言語と密接な関係にあります。 そのため、[ロケール](../c-runtime-library/locale.md)言語、国/地域、およびコード ページの一意の組み合わせは、します。 呼び出すことにより実行時に、ロケールとコード ページの設定を変更できる、 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)関数。  
  
 言語が異なると、コード ページも異なる場合があります。 たとえば、ANSI のコード ページ 1252 は英語やほとんどのヨーロッパ言語で使われていますが、日本語の漢字では ANSI のコード ページ 932 が使われています。 事実上すべてのコード ページは、下位 128 文字 (0x00 ～ 0x7F) の ASCII 文字セットを共有しています。  
  
 1 バイトのコード ページはいずれも、バイト値を文字 (数字や区切り記号を含む) やグリフに対応付けた、256 エントリのテーブルで表すことができます。 マルチバイトのコード ページも、2 バイト値を文字に対応付けた (64K エントリにもなる) 大きなテーブルとして表すことができます。 ただし実際は、これらのコード ページは、最初の 256 (1 バイト) 文字を対応付けたテーブルと 2 バイト値の範囲として表すのが一般的です。  
  
 コード ページの詳細については、「 [Code Pages](../c-runtime-library/code-pages.md)」を参照してください。  
  
 C のランタイム ライブラリには、ロケールとマルチバイトの 2 種類の内部コード ページが存在します。 プログラムの実行中に現在のコード ページを変更することができます (ドキュメントを参照して、 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)と[_setmbcp](../c-runtime-library/reference/setmbcp.md)関数)。 また、ランタイム ライブラリは、入手してのプログラムの実行中の定数は、オペレーティング システム コード ページの値を使用します。  
  
 ロケールのコード ページを変更すると、ロケールに依存する関数の動作は、そのコード ページで規定されている動作に変更されます。 ロケールに依存する関数はすべて、既定で、まず "C" ロケール固有のコード ページを基に動作します。 システム内部のロケールのコード ページもロケールに特有なその他の属性も、`setlocale` 関数を呼び出すことで変更できます。 `setlocale` (LC_ALL, "") を呼び出すと、オペレーティング システムのユーザー ロケールが示すロケールに設定されます。  
  
 同様に、マルチバイトのコード ページを変更すると、マルチバイト関数の動作は、そのコード ページで規定されている動作に変更されます。 既定では、マルチバイト関数はすべて、オペレーティング システム既定のコード ページに対応しているマルチバイト コード ページを使って動作します。 システム内部のマルチバイトのコード ページは、`_setmbcp` 関数を呼び出すことによって変更できます。  
  
 C のランタイム関数 `setlocale` は、現在のプログラムのロケール情報の一部または全部の設定、変更、および問い合わせが可能です。 [_Wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)ルーチンは、ワイド文字バージョンの`setlocale`; 引数と戻り値の`_wsetlocale`ワイド文字列です。  
  
## <a name="see-also"></a>関連項目  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [文字セットにおける移植性の利点](../text/benefits-of-character-set-portability.md)