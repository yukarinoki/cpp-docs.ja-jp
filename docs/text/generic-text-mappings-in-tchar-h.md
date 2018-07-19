---
title: Tchar.h における汎用テキスト マッピング |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- tchar.h
dev_langs:
- C++
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7ed29b03a37c9b911a954192152115b1458fd94
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33867104"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar.h における汎用テキストのマッピング
コードを簡単に国際対応にできるように、[!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] のランタイム ライブラリには、多くのデータ型やルーチンなどのオブジェクトに対して、[!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 固有の汎用テキストのマッピングが用意されています。 Tchar.h で定義されているこれらのマッピングを使用すると、[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] ステートメントで定義したマニフェスト定数に応じて、1 バイト、マルチバイト、`#define` のどの文字セットにも対応できるジェネリック コードを記述できます。 汎用テキスト マッピングは [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 固有の拡張機能であり、[!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] とは互換性がありません。  
  
 Tchar.h を使用することにより、同じソースから、1 バイト、マルチバイト文字セット (MBCS: Multibyte Character Set)、および [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] の各アプリケーションをビルドできます。 Tchar.h では、プレフィックス `_tcs` の付いたマクロが定義されており、正しいプリプロセッサ定義に応じて `str`、`_mbs`、`wcs` のいずれかの関数に割り当てられます。 MBCS でビルドするには、シンボル `_MBCS` を定義します。 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] でビルドするには、シンボル `_UNICODE` を定義します。 1 バイト アプリケーションをビルドする場合は、どちらも定義しません (既定)。 MFC アプリケーションでは、既定で `_MBCS` が定義されています。  
  
 `_TCHAR` データ型は、Tchar.h で条件に応じて定義されます。 ビルドで `_UNICODE` シンボルが定義されている場合、`_TCHAR` は `wchar_t` として定義されます。それ以外の場合、1 バイトおよび MBCS のビルドでは `char` として定義されます。 Unicode のワイド文字データ型である `wchar_t` は、8 ビットの符号付き `char` の 16 ビット版に相当します。国際対応のアプリケーションでは、バイトではなく `_tcs` を扱う `_TCHAR` ファミリの関数を使う必要があります。 たとえば、`_tcsncpy`コピー `n` `_TCHARs`ではなく、`n`バイトです。  
  
 1 バイト文字セット (SBCS: Single Byte Character Set) の文字列処理関数の中には、符号付きの `char*` パラメーターを受け取るものがあります。このため、`_MBCS` を定義すると、型の不一致を知らせるコンパイラの警告が生成される場合があります。 この警告を回避する方法は 3 つあります。  
  
1.  Tchar.h のタイプ セーフなインライン関数サンクを使用します。 これが既定の動作です。  
  
2.  コマンド ラインで `_MB_MAP_DIRECT` を定義して、Tchar.h の直接マクロを使用します。 この場合は、型を手作業で一致させる必要があります。 これは一番速い方法ですが、タイプ セーフではありません。  
  
3.  Tchar.h のタイプ セーフな静的リンク ライブラリ関数のサンクを使用します。 この場合は、コマンド ラインで定数 `_NO_INLINING` を定義します。 これは、一番時間がかかりますが、一番タイプ セーフな方法です。  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>汎用テキスト マッピング用のプリプロセッサ ディレクティブ  
  
|#define|コンパイル後の状態|例|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] (ワイド文字)|`_tcsrev` は `_wcsrev` に割り当てられます。|  
|`_MBCS`|マルチバイト文字|`_tcsrev` は `_mbsrev` に割り当てられます。|  
|なし (既定では `_UNICODE` も `_MBCS` も未定義)|SBCS ([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)])|`_tcsrev` は `strrev` に割り当てられます。|  
  
 たとえば、Tchar.h で定義されている汎用テキスト関数 `_tcsrev` は、プログラムで `_mbsrev` が定義されていると `_MBCS` になり、`_wcsrev` が定義されていると `_UNICODE` になります。 それ以外の場合、`_tcsrev` は `strrev` に割り当てられます。 プログラミングに便利なように他のデータ型のマッピングも Tchar.h に用意されていますが、`_TCHAR` が最も多く使用されます。  
  
### <a name="generic-text-data-type-mappings"></a>汎用テキストのデータ型のマップ  
  
|汎用テキスト<br /><br /> データ型名|_UNICODE &<br /><br /> _MBCS が未定義の場合|_MBCS<br /><br /> 定義済み|_UNICODE<br /><br /> 定義済み|  
|--------------------------------------|----------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` または `_TEXT`|影響なし (プリプロセッサによって削除される)|影響なし (プリプロセッサによって削除される)|`L` (後続の文字または文字列を対応する [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] の文字または文字列に変換する)|  
  
 汎用テキスト マップのルーチン、変数、およびその他のオブジェクトの一覧は、次を参照してください。[汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)ランタイム ライブラリ リファレンスです。  
  
> [!NOTE]
>  Unicode の文字列には NULL バイトが含まれている可能性があるため、この文字列と一緒に `str` ファミリの関数を使用しないでください。 同様に、MBCS (または SBCS) 文字列には `wcs` ファミリの関数を使用しないでください。  
  
 MBCS、`_TCHAR`、および SBCS の各モデルに対応するために、`_tcsrev` および [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] を使用するコード例を次に示します。  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 `_MBCS` が定義されていると、プリプロセッサによって次のコードに変換されます。  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 `_UNICODE` が定義されていると、プリプロセッサによって次のコードに変換されます。  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 `_MBCS` と `_UNICODE` のどちらも定義されていない場合、プリプロセッサは前のコードを次のように 1 バイトの [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] コードに割り当てます。  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 このように、1 つのソース コード ファイルを記述、保守、およびコンパイルすることで、3 種類のそれぞれの文字セットに固有のルーチンを実行できます。  
  
## <a name="see-also"></a>関連項目  
 [テキストと文字列](../text/text-and-strings-in-visual-cpp.md)   
 [_MBCS コードでの TCHAR.H データ型の使用](../text/using-tchar-h-data-types-with-mbcs-code.md)