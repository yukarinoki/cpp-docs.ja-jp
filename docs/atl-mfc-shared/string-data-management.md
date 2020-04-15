---
title: 文字列データ管理
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: 7f92b38ac659faef2dd9319b2f204ba837f0d473
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317465"
---
# <a name="string-data-management"></a>文字列データ管理

Visual C++ では、文字列データを管理する方法がいくつか用意されています。

- C スタイルの null で終わる文字列を操作するための文字列[操作](../c-runtime-library/string-manipulation-crt.md)

- 文字列を管理するための Win32 API 関数

- MFC の[クラス CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)は、柔軟で、変更可能な文字列オブジェクトを提供します。

- クラス[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)は、MFC に依存しない文字列オブジェクトを提供し、次の機能を持ちます。`CString`

ほとんどすべてのプログラムが文字列データを処理します。 MFC の`CString`クラスは、多くの場合、柔軟な文字列処理に最適なソリューションです。 バージョン 7.0 以降`CString`は、MFC または MFC に依存しないプログラムで使用できます。 Unicode または MBCS`CString`プログラミングのように、ランタイム ライブラリとサポート文字列の両方にマルチバイト (ワイド) 文字が含まれています。

この資料では、文字列操作に関連するクラス ライブラリが提供する汎用サービスについて説明します。 この記事で扱うトピックは次のとおりです。

- [ユニコードと MBCS の移植性を提供](#_core_unicode_and_mbcs_provide_portability)

- [C文字列と定数の文字ポインタ](#_core_cstrings_and_const_char_pointers)

- [C文字列参照カウント](#_core_cstring_reference_counting)

[CStringT クラスクラス](../atl-mfc-shared/reference/cstringt-class.md)は、文字列を操作するためのサポートを提供します。 C ランタイム ライブラリ文字列パッケージで通常提供される機能を置き換え、拡張することを目的としています。 この`CString`クラスは、Basic に示されているような、文字列処理を簡略化するためのメンバー関数と演算子を提供します。 また、このクラスには、s および標準 C++ 文字列データ型`CString`の構築、割り当て、および比較を行うためのコンストラクターと演算子も用意されています。 から`CString``CObject`派生したオブジェクトではないため、MFC `CString` (MFC) の大部分とは独立してオブジェクトを使用できます。

`CString`オブジェクトは"値のセマンティクス" に従います。 オブジェクト`CString`は、一意の値を表します。 a は`CString`文字列へのポインタではなく、実際の文字列と考えてください。

オブジェクト`CString`は、可変長の文字のシーケンスを表します。 `CString`オブジェクトは文字の配列と考えることができます。

## <a name="unicode-and-mbcs-provide-portability"></a><a name="_core_unicode_and_mbcs_provide_portability"></a>ユニコードと MBCS は移植性を提供します。

MFC バージョン 3.0 以降では、UNIcode 文字セットとマルチバイト文字セット (MBCS) の両方に対して、 を含む`CString`MFC が有効になります。 このサポートにより、Unicode 文字または ANSI 文字用に構築できる移植性の高いアプリケーションを簡単に作成できます。 この移植性を有効にするために、`CString`オブジェクト内の各文字は TCHAR 型であり、アプリケーション`wchar_t`のビルド時にシンボル _UNICODEを定義するか、または定義しない`char`かのように定義されます。 文字`wchar_t`は 16 ビット幅です。 シンボルを定義してビルドする場合は、MBCS _MBCS有効になります。 MFC 自体は、定義されている _MBCS シンボル (NAFX ライブラリの) または _UNICODE 記号 (UAFX ライブラリの場合) を使用して構築されます。

> [!NOTE]
> この`CString`例と文字列に付随する記事では、_T マクロを使用して Unicode 移植性のために適切にフォーマットされたリテラル文字列を示しています。

`L"literal string"`

> [!NOTE]
> コンパイラは Unicode 文字列として扱います。 コード例を次に示します。

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
> _UNICODE定義されている場合は Unicode 文字列として変換され、定義されていない場合は ANSI 文字列として変換されます。 詳細については、[ユニコードおよびマルチバイト文字セット (MBCS) サポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)を参照してください。

オブジェクト`CString`は、最大INT_MAX (2,147,483,647) 文字を格納できます。 TCHAR データ型は、`CString`オブジェクト内の個々の文字を取得または設定するために使用されます。 文字配列とは異なり`CString`、クラスにはメモリ割り当て機能が組み込まれています。 これにより、`CString`オブジェクトは必要に応じて自動的に拡張できます(つまり、長い文字列に合わせて`CString`オブジェクトを拡張する心配はありません)。

## <a name="cstrings-and-const-char-pointers"></a><a name="_core_cstrings_and_const_char_pointers"></a>C文字列と定数の文字ポインタ

オブジェクト`CString`は、リテラル C スタイルの文字列 (Unicode`PCXSTR`の下にない場合は**const char**<strong>\*</strong>と同じ) のように動作することもできます。 [CSimpleStringT::演算子 PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr)変換演算子`CString`を使用すると、関数呼び出しで文字ポインターを自由に置換できます。 **CString( LPCWSTR** `pszSrc` **)** コンストラクタを使用すると、文字ポインタを`CString`オブジェクトに置き換えることができます。

オブジェクトの折り畳みは`CString`試行されません。 を含む`CString``Chicago`2 つのオブジェクトを作成すると、`Chicago`の文字は 2 か所に格納されます。 (これは、将来のバージョンの MFC には当てはまらない可能性があるため、このバージョンに依存しないでください)。

> [!NOTE]
> 文字への非定数ポインターとして直接アクセスする必要がある場合は[、CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)`CString`関数と[CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)メンバー関数を使用します。

> [!NOTE]
> オートメーションで使用される BSTR オブジェクト (以前は OLE オートメーションと呼ばれていた) を割り当てて設定するには[、CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)および[CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring)メンバー関数を使用します。

> [!NOTE]
> 可能な場合は`CString`、ヒープではなくフレームにオブジェクトを割り当てます。 これにより、メモリが節約され、パラメータの受け渡しが簡素化されます。

この`CString`クラスは、Microsoft Foundation クラス ライブラリ コレクション クラスとして`CString`実装されていませんが、オブジェクトはコレクションに要素として格納できます。

## <a name="cstring-reference-counting"></a><a name="_core_cstring_reference_counting"></a>C文字列参照カウント

MFC バージョン 4.0 では[、CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトがコピーされると、MFC はデータをコピーするのではなく、参照カウントをインクリメントします。 これにより、値によるパラメーターの受け`CString`渡しと値によるオブジェクトの戻り方の効率が向上します。 これらの操作によって、コピー コンストラクターが複数回呼び出される場合があります。 参照カウントをインクリメントすると、これらの共通操作のオーバーヘッドが減少`CString`し、より魅力的なオプションを使用できます。

各コピーが破棄されると、元のオブジェクトの参照カウントが減分されます。 元`CString`のオブジェクトは、参照カウントが 0 に減らされるまで破棄されません。

メンバー関数`CString`[CSimpleStringT::ロックバッファ](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)を使用して、参照カウントを無効または有効にすることができます。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
