---
title: Unicode およびマルチバイト文字セット (MBCS) のサポート |Microsoft Docs
ms.custom: ''
ms.date: 1/09/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e9d212e74f77d21efa1b2ed030f8a1446d111fc
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882950"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート

日本語や中国語などの一部の言語は巨大な文字セットを扱います。 これらの市場向けのプログラミングをサポートするためには、Microsoft Foundation Class ライブラリ (MFC) は、大きなサイズの文字セットを処理する 2 つの異なるアプローチを有効にします。

- [Unicode](#mfc-support-for-unicode-strings)、`wchar_t`ベースのワイド文字と utf-16 としてエンコードされた文字列。

- [マルチバイト文字セット (MBCS)](#mfc-support-for-mbcs-strings)、 **char**ベースの 1 つまたは 2 バイト文字と文字列のロケール固有の文字セットにエンコードします。

Microsoft がすべての新しい開発用の MFC の Unicode ライブラリをお勧めして、MBCS ライブラリは、Visual Studio 2013 と Visual Studio 2015 で非推奨とされました。 現在のバージョンには該当しません。 Visual Studio 2017 では、MBCS の非推奨に関する警告が削除されました。

## <a name="mfc-support-for-unicode-strings"></a>MFC がサポートする Unicode 文字列

MFC クラス ライブラリ全体は、Unicode 文字とワイド文字に utf-16 として格納された文字列と条件付きで有効です。 具体的には、クラス[CString](../atl-mfc-shared/reference/cstringt-class.md)が Unicode 対応します。

これらのライブラリ、デバッガー、および DLL ファイルは、MFC で Unicode をサポートするために使用されます。

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*バージョン*U.LIB|MFC*バージョン*U.PDB|MFC*バージョン*U.DLL|MFC*バージョン*UD します。LIB|
|MFC*バージョン*UD します。PDB ファイル|MFC*バージョン*UD します。DLL|MFCS*バージョン*U.LIB|MFCS*バージョン*U.PDB|
|MFCS*バージョン*UD します。LIB|MFCS*バージョン*UD します。PDB ファイル|MFCM*バージョン*U.LIB|MFCM*バージョン*U.PDB|
|MFCM*バージョン*U.DLL|MFCM*バージョン*UD します。LIB|MFCM*バージョン*UD します。PDB ファイル|MFCM*version*UD.DLL|

(*バージョン*は、ファイルのバージョン番号を表すたとえば、'140'、バージョン 14.0)。

`CString` TCHAR データ型に基づきます。 TCHAR が型として定義されている場合は、プログラムのビルドのシンボル _UNICODE が定義されている、 `wchar_t`、16 ビットの文字エンコーディングの種類。 TCHAR として定義されている場合は、 **char**、通常の 8 ビット文字エン コードします。 このため、Unicode を使用するときは、`CString` を 16 ビット幅の文字で構成します。 型の文字の Unicode を使用しない構成は**char**します。

アプリケーションを Unicode 対応にするには、次のことも行う必要があります。

- _T マクロ条件によってリテラル文字列を使用して、Unicode に移植します。

- 文字列を引数として渡すときは、その関数が文字列の長さを文字数とバイト数のどちらで数えるのかを注意してください。 Unicode 文字列を使用するときは、文字数とバイト数の長さが異なります。

- C ランタイム ライブラリの文字列操作関数は Unicode 対応バージョンを使用してください。

- 文字および文字へのポインターには、以下の型を使用してください。

   - 使用する TCHAR を使用して、 **char**します。

   - 使用する LPTSTR を使用して、 **char\*** します。

   - 使用する LPCTSTR を使用して、 **const char\*** します。 `CString` 演算子の間で変換に LPCTSTR を提供`CString`LPCTSTR とします。

`CString` のコンストラクター、代入演算子、比較演算子は Unicode を適切に処理します。

[ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)文字列処理関数のすべてのポータブル バージョンを定義します。 詳細については、カテゴリを参照してください。[国際化](../c-runtime-library/internationalization.md)します。

## <a name="mfc-support-for-mbcs-strings"></a>MFC がサポートする MBCS 文字列

このクラス ライブラリではマルチバイト文字セットもサポートされていますが、サポートされているのは、2 バイト文字セット (DBCS: Double-Byte Character Sets) のみです。

マルチバイト文字セットでは、文字は 1 バイト幅または 2 バイト幅になります。 2 バイト幅の文字では 1 バイト目が "先行バイト" になり、特定の範囲の文字を含むコード ページを指定します。 先行バイトと 2 バイト目の "後続バイト" を組み合わせると、そのコードが表す文字が決まります。

プログラムのビルドのシンボル _MBCS が定義されている場合は、TCHAR を入力を`CString`ベースは、マップ**char**します。 _MBCS シンボルを定義したときは、`CString` 中のどのバイトが先行バイトであり、どのバイトが後続バイトであるかはプログラマが判定してください。 この判定用の関数は C ランタイム ライブラリで定義されています。

DBCS では、文字列の中に任意の ANSI の 1 バイト文字と 2 バイト文字を混在させることができます。 したがって、DBCS では文字列の解析時に特別な注意が必要です。 このようなリソースとして、`CString` オブジェクトがあります。

> [!NOTE]
> MFC における Unicode 文字列のシリアル化は、Unicode 文字列と MBCS 文字列の両方について、どちらのバージョンのアプリケーションを使用しているのかを考慮せずに読み込むことができます。 データ ファイルはプログラムの Unicode 版と MBCS 版の間で移植性があります。

`CString` のメンバー関数は、特別な "汎用テキスト" バージョンの C ランタイム ライブラリ関数を使用します。つまり、Unicode 対応の関数を使用します。 したがって、たとえば、`CString` のメンバー関数が通常 `strcmp` を呼び出す場所では、代わりに "汎用テキスト" 関数 `_tcscmp` を呼び出します。 _UNICODE、_MBCS のシンボルの定義方法に応じて`_tcscmp`次のようにマップされます。

|||
|-|-|
|_MBCS が定義されている場合|`_mbscmp`|
|_UNICODE が定義されている場合|`wcscmp`|
|どちらのシンボルも定義されていない場合|`strcmp`|

> [!NOTE]
> _UNICODE、_MBCS のシンボルは、相互に排他的です。

すべてのランタイム文字列処理ルーチンの汎用テキスト関数マッピングは、後ほど[C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)します。 一覧については、次を参照してください。[国際化](../c-runtime-library/internationalization.md)します。

同様に、`CString`メソッドは、汎用的なデータ型マッピングを使用して実装されます。 TCHAR を使用する MFC MBCS および Unicode の両方を有効にするには、 **char**または`wchar_t`の LPTSTR **char\*** または`wchar_t*`とに LPCTSTR **const char\*** または`const wchar_t*`します。 これによって、MBCS または Unicode への正しいマッピングが確保されます。

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[文字列操作](../c-runtime-library/string-manipulation-crt.md)  
