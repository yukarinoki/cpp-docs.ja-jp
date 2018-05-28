---
title: Unicode プログラミングの要約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a378d46c517dfc0fbb5857ad54bc31f4c34287b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="unicode-programming-summary"></a>Unicode プログラミングの要約
Unicode に対する MFC や C のランタイム機能のサポートを有効にするには、次のようにします。  
  
-   定義 **_UNICODE**です。  
  
     シンボルを定義する **_UNICODE**プログラムをビルドする前にします。  
  
-   エントリ ポイントを指定する。  
  
     **出力** ページで、プロジェクトの [リンカー] フォルダーの[プロパティ ページ](../ide/property-pages-visual-cpp.md) ダイアログ ボックスで、設定、エントリ ポイント シンボル**wWinMainCRTStartup**です。  
  
-   移植性の高いランタイム関数と型を使用する。  
  
     Unicode 文字列を取り扱う際は、必ず適切な C ランタイム関数を使います。 使用することができます、 **wcs**関数のファミリを使用しても、完全に移植可能な (国際対応の) **_TCHAR**マクロです。 これらのマクロは、すべて先頭に付きます **_tcs**;、置き換えると、1 つのいずれかの**str**ファミリの関数。 これらの関数がで詳しく説明されている、[国際化](../c-runtime-library/internationalization.md)のセクションで、*ランタイム ライブラリ リファレンス*です。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
     使用して **_TCHAR**しで説明されているポータブル関連のデータ型[Unicode のサポート](../text/support-for-unicode.md)です。  
  
-   リテラル文字列を正しく処理する。  
  
     Visual C++ コンパイラでは、次のリテラル文字列を  
  
    ```  
    L"this is a literal string"  
    ```  
  
     Unicode 文字の文字列として解釈します。 リテラル文字にも、同じプリフィックスを使うことができます。 使用して、 **_T** Unicode 環境下の Unicode 文字列または Unicode を含めない ANSI 文字列 (MBCS を含む) としてコンパイルするために一般的に、リテラル文字列をコーディングするマクロです。 たとえば、  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     を使う代わりに、  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     **_UNICODE**定義、 **_T**変換、リテラル文字列を L プレフィックスが付いた形式です。 それ以外の場合、 **_T** L プレフィックスを付けずに文字列を変換します。  
  
    > [!TIP]
    >  **_T**マクロと同じ、`_TEXT`マクロです。  
  
-   注意して文字列の長さを関数に渡す。  
  
     文字列の文字数を要求する関数もありますが、バイト数を要求する関数もあります。 たとえば場合、 **_UNICODE**が定義されている、次の呼び出し、`CArchive`オブジェクトは機能しません (`str`は、 `CString`)。  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     Unicode アプリケーションの場合、文字列の長さは文字数を表しますが、各文字が 2 バイト幅なので、正確なバイト数ではありません。 バイト数を渡す場合は、次のコードを記述する必要があります。  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     このコードにより、正確なバイト数を書き込むことができます。  
  
     これに対して、バイト指向ではなく文字指向の MFC メンバー関数の場合は、この補足コードがなくても正常に機能します。  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` は、バイト数ではなく文字数を取ります。  
  
-   使用して[fopen_s、_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)を unicode 形式のファイルを開きます。  
  
 要約すると、MFC とランタイム ライブラリは Unicode プログラミングの次のサポートを提供します。  
  
-   データベース クラスのメンバー関数を除いて、`CString` を含むすべての MFC 関数は、Unicode に対応しています。 また、`CString` には、Unicode/ANSI 変換関数も用意されています。  
  
-   ランタイム ライブラリには、すべての文字列操作関数の Unicode バージョンが用意されています。 (また、Unicode や MBCS に適した移植性の高いバージョンとして、 これらは、 **_tcs**マクロです)。  
  
-   Tchar.h には、ポータブル データ型および **_T**マクロ リテラル文字列と文字を変換するためです。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
-   ランタイム ライブラリのワイド文字バージョンを提供する**メイン**です。 使用して**wmain** Unicode 対応アプリケーションにします。  
  
## <a name="see-also"></a>関連項目  
 [Unicode のサポート](../text/support-for-unicode.md)