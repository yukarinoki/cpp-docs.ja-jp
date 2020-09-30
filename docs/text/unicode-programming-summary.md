---
title: Unicode プログラミングの要約
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
ms.openlocfilehash: 5095e1c58db3e5c35eb9215367f2fbb064bc228a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504711"
---
# <a name="unicode-programming-summary"></a>Unicode プログラミングの要約

Unicode に対する MFC や C のランタイム機能のサポートを有効にするには、次のようにします。

- `_UNICODE`を定義します。

   `_UNICODE`プログラムをビルドする前にシンボルを定義します。

- エントリ ポイントを指定する。

   プロジェクトの **[** [プロパティページ](../build/reference/property-pages-visual-cpp.md)] ダイアログボックスの [**リンカー** ] フォルダーの [詳細設定] ページで、[**エントリポイント**シンボル] をに設定し `wWinMainCRTStartup` ます。

- 移植性の高いランタイム関数と型を使用する。

   Unicode 文字列を取り扱う際は、必ず適切な C ランタイム関数を使います。 関数ファミリを使用することもでき `wcs` ますが、完全に移植可能な (国際対応の) マクロを使用することをお勧めし `_TCHAR` ます。 これらのマクロはすべてにプレフィックスとして付けられています。これらのマクロは、 `_tcs` `str` 関数のファミリに対して1つずつ置き換えます。 これらの関数の詳細については、「*ランタイムライブラリリファレンス*」の「[国際化](../c-runtime-library/internationalization.md)」セクションを参照してください。 詳細については、「 [tchar. h の汎用テキストマップ](../text/generic-text-mappings-in-tchar-h.md)」を参照してください。

   `_TCHAR`と、「 [Unicode のサポート](../text/support-for-unicode.md)」で説明されている、関連する移植性のあるデータ型を使用します。

- リテラル文字列を正しく処理する。

   Visual C++ コンパイラでは、次のリテラル文字列を

    ```cpp
    L"this is a literal string"
    ```

   Unicode 文字の文字列として解釈します。 リテラル文字にも、同じプリフィックスを使うことができます。 マクロは、リテラル文字列を汎用的にコーディングするために使用します。 unicode では、unicode 文字列として、unicode で `_T` はなく ANSI 文字列 (MBCS を含む) としてコンパイルされます。 たとえば、次の表記の代わりに、

    ```cpp
    pWnd->SetWindowText( "Hello" );
    ```

   を使う代わりに、

    ```cpp
    pWnd->SetWindowText( _T("Hello") );
    ```

   が `_UNICODE` 定義されている場合、 `_T` リテラル文字列を左辺のプレフィックス付きの形式に変換します。それ以外の場合は、 `_T` l プレフィックスなしで文字列を変換します。

    > [!TIP]
    >  `_T`マクロはマクロと同じです `_TEXT` 。

- 注意して文字列の長さを関数に渡す。

   文字列の文字数を要求する関数もありますが、バイト数を要求する関数もあります。 たとえば、が定義されている場合、 `_UNICODE` オブジェクトへの次の呼び出し `CArchive` は機能しません ( `str` はです `CString` )。

    ```cpp
    archive.Write( str, str.GetLength( ) );    // invalid
    ```

   Unicode アプリケーションの場合、文字列の長さは文字数を表しますが、各文字が 2 バイト幅なので、正確なバイト数ではありません。 バイト数を渡す場合は、次のコードを記述する必要があります。

    ```cpp
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid
    ```

   このコードにより、正確なバイト数を書き込むことができます。

   これに対して、バイト指向ではなく文字指向の MFC メンバー関数の場合は、この補足コードがなくても正常に機能します。

    ```cpp
    pDC->TextOut( str, str.GetLength( ) );
    ```

   `CDC::TextOut` は、バイト数ではなく文字数を取ります。

- Unicode ファイルを開くに [は、fopen_s、_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) を使用します。

要約すると、MFC とランタイムライブラリには、Unicode プログラミングの次のサポートが用意されています。

- データベース クラスのメンバー関数を除いて、`CString` を含むすべての MFC 関数は、Unicode に対応しています。 また、`CString` には、Unicode/ANSI 変換関数も用意されています。

- ランタイム ライブラリには、すべての文字列操作関数の Unicode バージョンが用意されています。 (また、Unicode や MBCS に適した移植性の高いバージョンとして、 これらは `_tcs` マクロです)。

- tchar.h には、ポータブルデータ型と、 `_T` リテラル文字列と文字を変換するためのマクロが用意されています。 詳細については、「 [tchar. h の汎用テキストマップ](../text/generic-text-mappings-in-tchar-h.md)」を参照してください。

- ランタイムライブラリには、のワイド文字バージョンが用意されて `main` います。 `wmain`を使用すると、アプリケーションを Unicode 対応にすることができます。

## <a name="see-also"></a>関連項目

[Unicode のサポート](../text/support-for-unicode.md)
