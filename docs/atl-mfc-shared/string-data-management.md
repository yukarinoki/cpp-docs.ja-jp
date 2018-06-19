---
title: データ管理の文字列 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acf14ebec5417179a94d0a6ffefdb473966f0c2e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361237"
---
# <a name="string-data-management"></a>文字列データ管理
Visual C には、文字列データを管理するいくつかの方法が用意されています。  
  
-   [文字列操作](../c-runtime-library/string-manipulation-crt.md)C スタイルの null で終わる文字列を操作するため  
  
-   文字列を管理するための Win32 API 関数  
  
-   Mfc の[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)、柔軟で、サイズ変更可能な文字列オブジェクトを提供します。  
  
-   クラス[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)と同じ機能を MFC に依存しない文字列オブジェクトを提供します。 `CString`  
  
 ほぼすべてのプログラムは、文字列データを操作します。 MFC の`CString`クラスは、柔軟な文字列処理の最適なソリューションでは多くの場合。 Version 7.0 以降を`CString`MFC または MFC に依存しないプログラムで使用できます。 ランタイム ライブラリと`CString`Unicode や MBCS のプログラミングと同様に、マルチバイト (ワイド) 文字を含む文字列をサポートします。  
  
 この記事では、文字列の操作に関連するクラス ライブラリを提供する汎用的なサービスについて説明します。 この記事で説明されているトピックは次のとおりです。  
  
-   [Unicode と MBCS 提供の移植性](#_core_unicode_and_mbcs_provide_portability)  
  
-   [Cstring と const char ポインター](#_core_cstrings_and_const_char_pointers)  
  
-   [CString の参照カウント](#_core_cstring_reference_counting)  
  
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)クラスは、文字列操作のためのサポートを提供します。 置換し、通常、C ランタイム ライブラリ文字列パッケージによって提供される機能を拡張しています。 `CString`クラス メンバー関数と演算子の似た Basic では、簡略化された文字列処理を提供します。 このクラスもコンス トラクターと演算子の提供を構築する、割り当て、および比較する**Cstring**と標準 C++ 文字列データ型。 `CString`から派生していない`CObject`、使用することができます`CString`ほとんどの Microsoft Foundation Class ライブラリ (MFC) とは別にオブジェクト。  
  
 `CString` オブジェクトは、「値のセマンティクスです」に従う A`CString`オブジェクトを一意の値を表します。 考えること、`CString`文字列へのポインターとしてではなく、実際の文字列として。  
  
 A`CString`オブジェクトは、可変個の文字のシーケンスを表します。 `CString` オブジェクトは、文字の配列として考えることができます。  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode と MBCS の移植性を提供します。  
 MFC バージョン 3.0 以降では、MFC では、インクルード`CString`Unicode とマルチバイト文字セット (MBCS) の両方に対して有効にします。 このサポートでは、Unicode または ANSI のいずれかの文字を構築することができるポータブル アプリケーションを作成するためのやすくなります。 この移植性の内の各文字を有効にする、`CString`オブジェクトの型が**TCHAR**、として定義されている`wchar_t`シンボルを定義する場合 **_UNICODE**アプリケーションをビルドするときに、`char`しない場合。 A`wchar_t`文字が 16 ビット幅。 シンボルでビルドする場合に、MBCS が有効になっている **_MBCS**定義します。 MFC 自体がいずれかでビルドされた、 **_MBCS** (NAFX ライブラリ) のシンボルまたは **_UNICODE** (UAFX ライブラリ) のシンボルを定義します。  
  
> [!NOTE]
>  `CString`の例では、これと Unicode の移植性のリテラル文字列が正しく書式設定文字列の表示の記事に付属するを使用して、 **_T**マクロをリテラル文字列形式を。  
  
 `L"literal string"`  
  
> [!NOTE]
>  コンパイラは、Unicode 文字列として扱います。 コード例を次に示します。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]  
  
> [!NOTE]
>  場合は、Unicode 文字列として変換 **_UNICODE**が定義されているか、文字列以外の場合、ANSI として。 詳細については、記事を参照してください。 [Unicode およびマルチバイト文字セット (MBCS) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)です。  
  
 A`CString`オブジェクトに格納できる最大**INT_MAX** (2,147, 483,647) 文字です。 **TCHAR**を取得または設定内の個々 の文字データ型が使用される、`CString`オブジェクト。 文字配列とは異なり、`CString`クラスには、組み込みのメモリ割り当てが可能です。 これにより、`CString`必要に応じて自動的に拡張するオブジェクト (つまり必要はありませんの増加について心配する、`CString`長い文字列に合わせてオブジェクト)。  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> Cstring と const char ポインター  
 A`CString`オブジェクトは、C スタイルのリテラル文字列のように機能できますも (、`PCXSTR`と同じである**const char\***  Unicode 下にない場合)。 [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr)変換演算子を使うと`CString`自由に関数呼び出しで文字へのポインターの代わりに使用するオブジェクト。 **CString (LPCWSTR** `pszSrc` **)** コンス トラクターの代わりに使用する文字へのポインターを使用する`CString`オブジェクト。  
  
 行われませんフォールドに`CString`オブジェクト。 2 つの操作を行う場合`CString`オブジェクトを含む`Chicago`など、内の文字`Chicago`2 か所に格納されます。 (これではありません、MFC の将来のバージョンの場合は true。 それに依存しないようにするためです。)  
  
> [!NOTE]
>  使用して、 [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)メンバー関数に直接アクセスする必要がある場合、`CString`文字への非定数ポインターとして。  
  
> [!NOTE]
>  使用して、 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)と[名称](../atl-mfc-shared/reference/cstringt-class.md#setsysstring)メンバー関数を割り当てて設定`BSTR`オートメーション (以前の OLE オートメーション) で使用されるオブジェクト。  
  
> [!NOTE]
>  可能であれば、割り当てる`CString`ヒープではなく、フレームのオブジェクト。 これにより、メモリを節約し、パラメーターの引き渡しを簡略化します。  
  
 `CString`クラスとしては実装されません Microsoft Foundation Class ライブラリ コレクション クラス、ただし`CString`オブジェクトをコレクション内の要素として確実に格納することができます。  
  
##  <a name="_core_cstring_reference_counting"></a> CString の参照カウント  
 MFC バージョン 4.0 の時点でとき[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトのコピーは、MFC は、データをコピーするのではなく、参照カウントをインクリメントします。 これにより、値を返す、パラメーターの引き渡し`CString`より効率的な値でオブジェクト。 これらの操作を呼び出せる、場合によっては複数回コピー コンス トラクターが発生します。 これらの一般的な操作には、そのオーバーヘッドが軽減されを使用して参照カウントをインクリメント`CString`もより魅力的なオプションです。  
  
 各コピーは破棄されると、元のオブジェクト内の参照カウントは減少します。 元の`CString`オブジェクトは、参照カウントがゼロになるまでは破棄されません。  
  
 使用することができます、`CString`メンバー関数[CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)参照カウントを有効または無効にします。  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

