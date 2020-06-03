---
title: 'Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート'
ms.date: 01/09/2017
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.openlocfilehash: e1b93a3540cba553afd8f133c18496bddbd561b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317434"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート

日本語や中国語などの一部の言語は巨大な文字セットを扱います。 これらの市場向けのプログラミングをサポートするために、MFC (MFC) では、大きな文字セットを処理するための 2 つの異なるアプローチが可能になります。

- [Unicode](#mfc-support-for-unicode-strings)`wchar_t`ベースのワイド文字と文字列を UTF-16 としてエンコードします。

- [マルチバイト文字セット (MBCS)](#mfc-support-for-mbcs-strings)、**文字**ベースの 1 バイト文字または 2 バイト文字、およびロケール固有の文字セットでエンコードされた文字列。

マイクロソフトは、すべての新しい開発のための MFC ユニコード ライブラリを推奨しており、MBCS ライブラリは、Visual Studio 2013 および Visual Studio 2015 で非推奨でした。 この点は変更されました。 MBCS 廃止の警告は、Visual Studio 2017 で削除されました。

## <a name="mfc-support-for-unicode-strings"></a>MFC がサポートする Unicode 文字列

MFC クラス ライブラリ全体は、条件付きで Unicode 文字と文字列を UTF-16 としてワイド文字で格納できます。 特に、[クラス CString](../atl-mfc-shared/reference/cstringt-class.md)は Unicode 対応です。

MFC で Unicode をサポートするために、次のライブラリ、デバッガー、および DLL ファイルが使用されます。

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*バージョン*U.LIB|MFC*バージョン*U.PDB|MFC*バージョン*U.DLL|MFC*バージョン*UD.Lib|
|MFC*バージョン*UD.Pdb|MFC*バージョン*UD.Dll|MFCS*バージョン*U.LIB|MFCS*バージョン*U.PDB|
|MFCS*バージョン*UD.Lib|MFCS*バージョン*UD.Pdb|MFCM*バージョン*U.LIB|MFCM*バージョン*U.PDB|
|MFCM*バージョン*U.DLL|MFCM*バージョン*UD.Lib|MFCM*バージョン*UD.Pdb|MFCM*バージョン*UD.Dll|

(*バージョン*はファイルのバージョン番号を表します。例えば、「140」はバージョン14.0を意味します)。

`CString`は TCHAR データ型に基づいています。 プログラムのビルドにシンボル _UNICODEが定義されている場合、TCHAR は type `wchar_t`、16 ビット文字エンコード型として定義されます。 それ以外の場合、TCHAR は**char**、通常の 8 ビット文字エンコーディングとして定義されます。 このため、Unicode を使用するときは、`CString` を 16 ビット幅の文字で構成します。 Unicode を使用しない場合は、 **char**型の文字で構成されます。

アプリケーションを Unicode 対応にするには、次のことも行う必要があります。

- _T マクロを使用して、リテラル文字列を Unicode に移植可能な文字列として条件付きでコーディングします。

- 文字列を引数として渡すときは、その関数が文字列の長さを文字数とバイト数のどちらで数えるのかを注意してください。 Unicode 文字列を使用するときは、文字数とバイト数の長さが異なります。

- C ランタイム ライブラリの文字列操作関数は Unicode 対応バージョンを使用してください。

- 文字および文字へのポインターには、以下の型を使用してください。

  - **文字**を使用する場所には TCHAR を使用します。

  - **char**<strong>\*</strong>を使用する場所で LPTSTR を使用します。

  - **const char**<strong>\*</strong>を使用する場所で LPCTSTR を使用します。 `CString`との間`CString`で変換する演算子 LPCTSTR を提供します。

`CString` のコンストラクター、代入演算子、比較演算子は Unicode を適切に処理します。

[ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)では、すべての文字列処理関数の移植可能なバージョンを定義します。 詳細については、「[国際化](../c-runtime-library/internationalization.md)」カテゴリを参照してください。

## <a name="mfc-support-for-mbcs-strings"></a>MFC がサポートする MBCS 文字列

このクラス ライブラリではマルチバイト文字セットもサポートされていますが、サポートされているのは、2 バイト文字セット (DBCS: Double-Byte Character Sets) のみです。

マルチバイト文字セットでは、文字は 1 バイト幅または 2 バイト幅になります。 2 バイト幅の文字では 1 バイト目が "先行バイト" になり、特定の範囲の文字を含むコード ページを指定します。 先行バイトと 2 バイト目の "後続バイト" を組み合わせると、そのコードが表す文字が決まります。

プログラムのビルドにシンボル _MBCSが定義されている場合`CString`は、TCHAR と入力します。 **char** _MBCS シンボルを定義したときは、`CString` 中のどのバイトが先行バイトであり、どのバイトが後続バイトであるかはプログラマが判定してください。 この判定用の関数は C ランタイム ライブラリで定義されています。

DBCS では、文字列の中に任意の ANSI の 1 バイト文字と 2 バイト文字を混在させることができます。 したがって、DBCS では文字列の解析時に特別な注意が必要です。 このようなリソースとして、`CString` オブジェクトがあります。

> [!NOTE]
> MFC における Unicode 文字列のシリアル化は、Unicode 文字列と MBCS 文字列の両方について、どちらのバージョンのアプリケーションを使用しているのかを考慮せずに読み込むことができます。 データ ファイルはプログラムの Unicode 版と MBCS 版の間で移植性があります。

`CString` のメンバー関数は、特別な "汎用テキスト" バージョンの C ランタイム ライブラリ関数を使用します。つまり、Unicode 対応の関数を使用します。 したがって、たとえば、`CString` のメンバー関数が通常 `strcmp` を呼び出す場所では、代わりに "汎用テキスト" 関数 `_tcscmp` を呼び出します。 シンボル_MBCSおよび_UNICODEの定義方法に応じて、`_tcscmp`次のようにマップされます。

|||
|-|-|
|_MBCS が定義されている場合|`_mbscmp`|
|_UNICODE が定義されている場合|`wcscmp`|
|どちらのシンボルも定義されていない場合|`strcmp`|

> [!NOTE]
> シンボル_MBCSと_UNICODEは相互に排他的です。

すべてのランタイム文字列処理ルーチンの汎用テキスト関数マッピングについては[、「C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)」を参照してください。 一覧については、[国際化](../c-runtime-library/internationalization.md)を参照してください。

同様に`CString`、メソッドは、汎用データ型のマッピングを使用して実装されます。 MBCS と Unicode の両方を有効にするために、MFC`wchar_t`は **、文字**に TCHAR を使用し、**文字**<strong>\*</strong>に LPTSTR 、または`wchar_t*`**定数の文字**<strong>\*</strong>または`const wchar_t*`定数の場合は LPCTSTR を使用します。 これによって、MBCS または Unicode への正しいマッピングが確保されます。

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[文字列操作](../c-runtime-library/string-manipulation-crt.md)
