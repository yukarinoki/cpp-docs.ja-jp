---
title: Unicode およびマルチバイト文字セット (MBCS) のサポート |Microsoft ドキュメント
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
ms.openlocfilehash: 8492e4a6777e4d609e3b457cfc77d1b8a691eed3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート

日本語や中国語などの一部の言語は巨大な文字セットを扱います。 これらの市場向けのプログラミングをサポートするためには、Microsoft Foundation Class ライブラリ (MFC) は、大きなサイズの文字セットを処理する 2 つの異なる方法を有効にします。

- [Unicode](#mfc-support-for-unicode-strings)、`wchar_t`ベースのワイド文字と utf-16 としてエンコードされた文字列。

- [マルチバイト文字セット (MBCS)](#mfc-support-for-mbcs-strings)、`char`ベースの 1 つまたは 2 バイト文字と文字列のロケール固有の文字セットにエンコードします。

Microsoft がすべての新しい開発では、MFC の Unicode ライブラリをお勧めし、Visual Studio 2013 と Visual Studio 2015 で、MBCS ライブラリが推奨されていません。 現在のバージョンには該当しません。 Visual Studio 2017 で MBCS 廃止警告が削除されています。

## <a name="mfc-support-for-unicode-strings"></a>MFC がサポートする Unicode 文字列

MFC クラス ライブラリ全体は、Unicode 文字とワイド文字に utf-16 として格納された文字列と条件付きで有効です。 具体的には、クラス[CString](../atl-mfc-shared/reference/cstringt-class.md)が Unicode に対応します。

これらのライブラリ、デバッガー、および DLL ファイルは、MFC で Unicode をサポートするために使用されます。

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*バージョン*U.LIB|MFC*バージョン*U.PDB|MFC*バージョン*U.DLL|MFC*バージョン*UD です。LIB|
|MFC*バージョン*UD です。PDB ファイル|MFC*バージョン*UD です。DLL|MFCS*バージョン*U.LIB|MFCS*バージョン*U.PDB|
|MFCS*バージョン*UD です。LIB|MFCS*バージョン*UD です。PDB ファイル|MFCM*バージョン*U.LIB|MFCM*バージョン*U.PDB|
|MFCM*バージョン*U.DLL|MFCM*バージョン*UD です。LIB|MFCM*バージョン*UD です。PDB ファイル|MFCM*version*UD.DLL|

(*バージョン*ファイルのバージョン番号を表す例えば '140' は、バージョン 14.0)。

`CString` は `TCHAR` データ型に基づいています。 プログラムをビルドするときに `_UNICODE` シンボルが定義されている場合、`TCHAR` は、16 ビット文字エンコードの `wchar_t` 型として定義されます。 それ以外の場合、`TCHAR` は、通常の 8 ビット文字エンコードである `char` として定義されます。 このため、Unicode を使用するときは、`CString` を 16 ビット幅の文字で構成します。 Unicode を使用しないときは、`char` 型文字で構成します。

アプリケーションを Unicode 対応にするには、次のことも行う必要があります。

- 条件によってリテラル文字列を Unicode に移植するときは `_T` マクロを使用します。

- 文字列を引数として渡すときは、その関数が文字列の長さを文字数とバイト数のどちらで数えるのかを注意してください。 Unicode 文字列を使用するときは、文字数とバイト数の長さが異なります。

- C ランタイム ライブラリの文字列操作関数は Unicode 対応バージョンを使用してください。

- 文字および文字へのポインターには、以下の型を使用してください。

   - 使用して`TCHAR`を使用する`char`です。

   - 使用して`LPTSTR`を使用する`char*`です。

   - 使用して`LPCTSTR`を使用する`const char*`です。 `CString` には、`LPCTSTR` と `CString` を相互に変換するための、演算子 `LPCTSTR` が用意されています。

`CString` のコンストラクター、代入演算子、比較演算子は Unicode を適切に処理します。

[ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)文字列処理関数のすべてのポータブル バージョンを定義します。 詳細については、カテゴリを参照してください。[国際化](../c-runtime-library/internationalization.md)です。

## <a name="mfc-support-for-mbcs-strings"></a>MFC がサポートする MBCS 文字列

このクラス ライブラリではマルチバイト文字セットもサポートされていますが、サポートされているのは、2 バイト文字セット (DBCS: Double-Byte Character Sets) のみです。

マルチバイト文字セットでは、文字は 1 バイト幅または 2 バイト幅になります。 2 バイト幅の文字では 1 バイト目が "先行バイト" になり、特定の範囲の文字を含むコード ページを指定します。 先行バイトと 2 バイト目の "後続バイト" を組み合わせると、そのコードが表す文字が決まります。

プログラムをビルドするときに `_MBCS` シンボルが定義されていると、`TCHAR` 型 (`CString` はこの型に基づいています) は `char` 型にマップされます。 _MBCS シンボルを定義したときは、`CString` 中のどのバイトが先行バイトであり、どのバイトが後続バイトであるかはプログラマが判定してください。 この判定用の関数は C ランタイム ライブラリで定義されています。

DBCS では、文字列の中に任意の ANSI の 1 バイト文字と 2 バイト文字を混在させることができます。 したがって、DBCS では文字列の解析時に特別な注意が必要です。 このようなリソースとして、`CString` オブジェクトがあります。

> [!NOTE]
> MFC における Unicode 文字列のシリアル化は、Unicode 文字列と MBCS 文字列の両方について、どちらのバージョンのアプリケーションを使用しているのかを考慮せずに読み込むことができます。 データ ファイルはプログラムの Unicode 版と MBCS 版の間で移植性があります。

`CString` のメンバー関数は、特別な "汎用テキスト" バージョンの C ランタイム ライブラリ関数を使用します。つまり、Unicode 対応の関数を使用します。 したがって、たとえば、`CString` のメンバー関数が通常 `strcmp` を呼び出す場所では、代わりに "汎用テキスト" 関数 `_tcscmp` を呼び出します。 シンボル `_MBCS` および `_UNICODE` の定義状況に応じて、`_tcscmp` は次のようにマップされます。

|||
|-|-|
|`_MBCS` の定義|`_mbscmp`|
|`_UNICODE` の定義|`wcscmp`|
|どちらのシンボルも定義されていない場合|`strcmp`|

> [!NOTE]
> シンボル `_MBCS` と `_UNICODE` は同時に使用できません。

汎用テキスト関数マッピングがすべての実行時間の文字列操作ルーチンは、後ほど[C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)です。 一覧については、次を参照してください。[国際化](../c-runtime-library/internationalization.md)です。

同様に、`CString`メソッドは、汎用的なデータ型マッピングを使用して実装します。 MFC を使用するには MBCS と Unicode の両方を有効にする、`TCHAR`の`char`または`wchar_t`、`LPTSTR`の`char*`または`wchar_t*`、および`LPCTSTR`の`const char*`または`const wchar_t*`です。 これによって、MBCS または Unicode への正しいマッピングが確保されます。

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[文字列操作](../c-runtime-library/string-manipulation-crt.md)  
