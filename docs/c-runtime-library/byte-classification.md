---
description: '詳細情報: バイト分類'
title: バイト分類
ms.date: 04/04/2018
f1_keywords:
- c.types.bytes
helpviewer_keywords:
- code page 932
- byte classification routines
- bytes, testing
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
ms.openlocfilehash: 00691ca85366c5cbbe28b023f2a269838128fe9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221697"
---
# <a name="byte-classification"></a>バイト分類

これらの各ルーチンは、マルチバイト文字の指定されたバイトが条件を満たすかどうかをテストします。 特に指定がない場合、出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳しくは、「[setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。

> [!NOTE]
> 定義上、0 から 127 の間の ASCII 文字は、すべてのマルチバイト文字セットのサブセットと考えることができます。 たとえば、日本語のカタカナ文字セットには ASCII 文字と非 ASCII 文字が含まれています。

次の表の定義済み定数は、で定義されてい \<ctype.h> ます。

## <a name="multibyte-character-byte-classification-routines"></a>マルチバイト文字のバイト分類ルーチン

|ルーチンによって返される値|バイト テスト条件|
|-------------|-------------------------|
|[isleadbyte、_isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|先行バイト: テスト結果は、現在のロケールの **LC_CTYPE** カテゴリの設定に依存します|
|[_ismbbalnum、_ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|**isalnum** &#124;&#124; **_ismbbkalnum**|
|[_ismbbalpha、_ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|**isalpha** &#124;&#124; **_ismbbkalnum**|
|[_ismbbgraph、_ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|**_ismbbgraph** は、**_ismbbprint** と同じですが、空白文字 (0x20) は含みません|
|[_ismbbkalnum、_ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|区切り記号以外の非 ASCII テキストの記号。 たとえば、コード ページ 932 でのみ **_ismbbkalnum** は、カタカナ英数字をテストします|
|[_ismbbkana、_ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|カタカナ (0xA1 - 0xDF)、コード ページ 932 のみ|
|[_ismbbkprint、_ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|非 ASCII テキストまたは ASCII 以外の区切り記号。 たとえば、コード ページ 932 でのみ、**_ismbbkprint** はカタカナの英数字、またはカタカナの句読点 (範囲: 0xA1 - 0xDF) をテストします。|
|[_ismbbkpunct、_ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|ASCII 以外の区切り記号。 たとえば、コード ページ 932 でのみ **_ismbbkpunct** は、カタカナ区切り文字をテストします。|
|[_ismbblead、_ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|マルチバイト文字の最初のバイト。 たとえば、コード ページ 932 でのみ、有効な範囲は 0x81 - 0x9F、0xE0 - 0xFC です。|
|[_ismbbprint、_ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|**isprint** &#124;&#124; **_ismbbkprint**. **ismbbprint には** には、空白文字 (0x20) が含まれます。|
|[_ismbbpunct、_ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|**ispunct** &#124;&#124; **_ismbbkpunct**|
|[_ismbbtrail、_ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|マルチバイト文字の 2 番目のバイト。 たとえば、コード ページ 932 でのみ、有効な範囲は 0x40 - 0x7E、0x80 - 0xEC です。|
|[_ismbslead、_ismbslead_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|先行バイト (文字列コンテキストで)|
|[ismbstrail、_ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|末尾バイト (文字列コンテキストで)|
|[_mbbtype、_mbbtype_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|前のバイトに基づいて、バイトの種類を返します|
|[_mbsbtype、_mbsbtype_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|文字列内のバイトの種類を返します|
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|マルチバイト文字の変換状態を追跡します。|

に定義されている **MB_LEN_MAX** マクロは、 \<limits.h> マルチバイト文字で使用できる最大長 (バイト単位) に拡張されます。 で定義された **MB_CUR_MAX** は \<stdlib.h> 、現在のロケールのマルチバイト文字の最大長をバイト単位で拡張します。

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
