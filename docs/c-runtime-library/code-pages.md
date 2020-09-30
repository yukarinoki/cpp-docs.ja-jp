---
title: コード ページ
description: Microsoft C ランタイムでのコードページのサポートに関する説明。
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], code pages
- ANSI [C++], code pages
- system-default code page
- multibyte code pages [C++]
- localization [C++], code pages
- code pages [C++], types of
- locale code pages [C++]
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
ms.openlocfilehash: 1f9d311ec714d2043e072cbbfbac505d3f804294
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590070"
---
# <a name="code-pages"></a>コード ページ

"*コード ページ*" は文字セットです。数字、句読点、その他のグリフを入れることができます。 言語やロケールが異なると、コード ページも異なる場合があります。 たとえば、ANSI コード ページ 1252 は英語やほとんどのヨーロッパ言語で使われていますが、日本語の漢字には OEM コード ページ 932 が使われています。

コードページは、1バイトまたはマルチバイト値への文字のマッピングとして表形式で表すことができます。 多くのコード ページは、範囲 0x00 - 0x7F の文字に関して、ASCII 文字セットを共有しています。

Microsoft ランタイムライブラリでは、次の種類のコードページが使用されます。

- システム既定の ANSI コード ページ。 既定では、ランタイムシステムは、マルチバイトコードページを、オペレーティングシステムから取得されるシステム既定の ANSI コードページに自動的に設定します。 呼び出し:

    ```C
    setlocale ( LC_ALL, "" );
    ```

   また、システム既定の ANSI コード ページにロケールを設定します。

- ロケールのコード ページ。 ランタイム ルーチンの動作は、ロケール コード ページを含む、現在のロケール設定に依存します。 (詳細については、「 [ロケールに依存するルーチン](../c-runtime-library/locale.md)」を参照してください)。既定では、Microsoft ランタイムライブラリのすべてのロケールに依存するルーチンは、"C" ロケールに対応するコードページを使用します。 実行時には、 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)の呼び出しで使用中のロケールコードページを変更または照会できます。

- マルチバイト コード ページ。 ランタイム ライブラリのマルチバイト文字のほとんどの動作は、現在のマルチバイト コード ページ設定に依存します。 既定では、これらのルーチンではシステム既定の ANSI コード ページが使用されます。 実行時に、[_getmbcp](../c-runtime-library/reference/getmbcp.md) と [_setmbcp](../c-runtime-library/reference/setmbcp.md) でマルチバイト コード ページをそれぞれ照会または変更できます。

- "C" ロケールは、従来、C プログラムが実行されていたロケールに対応するよう、ANSI により定義されます。 "C" ロケールのコード ページ ("C" コード ページ) は ASCII 文字セットに対応します。 たとえば、"C" ロケールでは、**islower** は値 0x61 - 0x7A にのみ true を返します。 別のロケールでは、 **islower** は、 `true` そのロケールで定義されているように、これらの値およびその他の値に対してを返すことがあります。

## <a name="see-also"></a>関連項目

[プロパティー](../c-runtime-library/internationalization.md)\
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
