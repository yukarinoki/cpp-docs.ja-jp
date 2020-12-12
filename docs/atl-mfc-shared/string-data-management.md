---
description: 詳細については、「文字列データ管理」を参照してください。
title: 文字列データ管理
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: 37a3a13dc58641cc23e8ea5c31e12a4d4d9582fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166513"
---
# <a name="string-data-management"></a>文字列データ管理

Visual C++ は、文字列データを管理するいくつかの方法を提供します。

- C スタイルの null で終わる文字列を操作するための[文字列操作](../c-runtime-library/string-manipulation-crt.md)

- 文字列を管理するための Win32 API 関数

- 柔軟でサイズ変更可能な文字列オブジェクトを提供する、MFC クラスの[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)

- クラス [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)。これは、と同じ機能を持つ MFC に依存しない文字列オブジェクトを提供します。 `CString`

ほぼすべてのプログラムは、文字列データを操作します。 多くの `CString` 場合、MFC のクラスは柔軟な文字列処理に最適なソリューションです。 バージョン7.0 以降では、 `CString` mfc または mfc に依存しないプログラムでを使用できます。 `CString`Unicode または MBCS プログラミングのように、ランタイムライブラリとの両方で、マルチバイト (ワイド) 文字を含む文字列をサポートします。

この記事では、クラスライブラリが文字列操作に関連する汎用サービスについて説明します。 この記事では、次のトピックについて説明します。

- [Unicode と MBCS は移植性を備えています](#_core_unicode_and_mbcs_provide_portability)

- [CStrings と const char ポインター](#_core_cstrings_and_const_char_pointers)

- [CString 参照カウント](#_core_cstring_reference_counting)

[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)は、文字列を操作するためのサポートを提供します。 これは、C ランタイムライブラリの文字列パッケージによって提供される機能を置き換えると共に拡張することを目的としています。 クラスは、 `CString` 単純な文字列処理を行うためのメンバー関数と演算子を提供します。これは、Basic の場合と似ています。 また、クラスには、 `CString` s および標準 C++ 文字列データ型の構築、割り当て、および比較を行うためのコンストラクターと演算子も用意されています。 `CString`はから派生していないため `CObject` 、 `CString` Microsoft Foundation Class ライブラリのほとんど (MFC) とは無関係にオブジェクトを使用できます。

`CString` オブジェクトは "値のセマンティクス" に従います。 オブジェクトは、 `CString` 一意の値を表します。 は、 `CString` 文字列へのポインターとしてではなく、実際の文字列と考えることができます。

オブジェクトは、 `CString` 可変個の文字のシーケンスを表します。 `CString` オブジェクトは、文字の配列と考えることができます。

## <a name="unicode-and-mbcs-provide-portability"></a><a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode と MBCS は移植性を備えています

MFC バージョン3.0 以降では、を含む MFC `CString` が Unicode とマルチバイト文字セット (MBCS) の両方に対して有効になっています。 このサポートにより、Unicode または ANSI 文字用に作成できるポータブルアプリケーションを簡単に作成できます。 この移植性を実現するために、オブジェクト内の各文字 `CString` は TCHAR 型になります。これは、 **`wchar_t`** アプリケーションをビルドするときにシンボル _UNICODE を定義する場合と同様に定義され **`char`** ます。 **`wchar_t`** 文字は16ビット幅です。 シンボル _MBCS 定義されたを使用してビルドすると、MBCS が有効になります。 MFC 自体は、_MBCS 記号 (NAFX ライブラリの場合) または定義済みの _UNICODE シンボル (UAFX ライブラリの場合) のいずれかを使用して構築されます。

> [!NOTE]
> `CString`この記事および文字列に付随する記事の例では、リテラル文字列を形式に変換する _T マクロを使用して、Unicode 移植性のために適切に書式設定されたリテラル文字列を示しています。

`L"literal string"`

> [!NOTE]
> コンパイラが Unicode 文字列として処理します。 コード例を次に示します。

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
> は、_UNICODE が定義されている場合は Unicode 文字列として変換され、それ以外の場合は ANSI 文字列として変換されます。 詳細については、「 [Unicode およびマルチバイト文字セット (MBCS) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)」を参照してください。

オブジェクトには、 `CString` 最大 INT_MAX (2147483647) の文字を格納できます。 TCHAR データ型は、オブジェクト内の個々の文字を取得または設定するために使用され `CString` ます。 文字配列とは異なり、クラスには `CString` メモリ割り当て機能が組み込まれています。 これにより `CString` 、必要に応じてオブジェクトを自動的に拡張することができます (つまり、長い文字列に合わせてオブジェクトを拡張することを心配する必要はありません `CString` )。

## <a name="cstrings-and-const-char-pointers"></a><a name="_core_cstrings_and_const_char_pointers"></a> CStrings と const char ポインター

`CString`また、オブジェクトはリテラル C スタイルの文字列 ( `PCXSTR` Unicode でない場合は **const char** と同じ) のように動作することもでき <strong>\*</strong> ます。 [CSimpleStringT:: operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr)変換演算子を使用 `CString` すると、関数呼び出しの文字ポインターに対してオブジェクトを自由に置き換えることができます。 **CString (LPCWSTR** `pszSrc` **)** コンストラクターを使用すると、オブジェクトの文字ポインターを置き換えることができ `CString` ます。

オブジェクトをフォールドしようとしていません `CString` 。 たとえば、を含む2つのオブジェクトを作成した場合、の `CString` `Chicago` 文字は `Chicago` 2 か所に格納されます。 (これは、将来のバージョンの MFC には当てはまりません。そのため、これに依存しないようにしてください)。

> [!NOTE]
> 文字への非定数ポインターとしてに直接アクセスする必要がある場合は、 [CSimpleStringT:: GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) および [CSimpleStringT:: releasebuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) メンバー関数を使用し `CString` ます。

> [!NOTE]
> オートメーション (以前の OLE オートメーション) で使用される BSTR オブジェクトの割り当てと設定を行うには、 [cstringt:: allocsysstring](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) および [Cstringt:: setsysstring](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) メンバー関数を使用します。

> [!NOTE]
> 可能であれば、 `CString` ヒープではなく、フレームにオブジェクトを割り当てます。 これにより、メモリが節約され、パラメーターの受け渡しが簡単になります。

`CString`クラスは Microsoft Foundation Class ライブラリ collection クラスとして実装されていませんが、 `CString` オブジェクトをコレクションに要素として格納することは確かです。

## <a name="cstring-reference-counting"></a><a name="_core_cstring_reference_counting"></a> CString 参照カウント

MFC バージョン4.0 の時点で、 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md) オブジェクトがコピーされると、mfc はデータをコピーするのではなく、参照カウントをインクリメントします。 これにより、パラメーターを値で渡し、 `CString` オブジェクトを値でより効率的に返すことができます。 これらの操作により、コピーコンストラクターが呼び出され、場合によっては複数回呼び出されます。 参照カウントをインクリメントすると、これらの一般的な操作のオーバーヘッドが削減され、より魅力的なオプションを使用できるようになり `CString` ます。

各コピーが破棄されると、元のオブジェクトの参照カウントがデクリメントされます。 元の `CString` オブジェクトは、参照カウントが0になるまで破棄されません。

`CString`メンバー関数[CSimpleStringT:: lockbuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[CSimpleStringT:: UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)を使用して、参照カウントを無効または有効にすることができます。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
