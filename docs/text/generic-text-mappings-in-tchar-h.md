---
title: tchar.h における汎用テキストのマッピング
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
ms.openlocfilehash: bf872df2e6fb49e64a973e8799eef98dec1cb472
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361344"
---
# <a name="generic-text-mappings-in-tcharh"></a>tchar.h における汎用テキストのマッピング

国際化用コードの転送を簡素化するために、Microsoft ランタイム ライブラリには、多くのデータ型、ルーチン、およびその他のオブジェクトに対応する Microsoft 固有の汎用テキスト マッピングが用意されています。 ステートメントを使用して定義するマニフェスト定数に応じて、tchar.h で定義されているこれらのマッピングを使用して、1 バイト、マルチバイト、または Unicode 文字セット用にコンパイルできる汎用コードを`#define`記述できます。 汎用テキスト マッピングは Microsoft 固有の拡張機能であり、ANSI とは互換性がありません。

tchar.h を使用すると、同じソースからシングルバイト、マルチバイト文字セット (MBCS)、および Unicode アプリケーションを構築できます。 tchar.h は、適切なプリプロセッサ`_tcs`定義を使用して、 、`str``_mbs`または`wcs`関数に対応付けるマクロ ( 接頭部を持つ ) を定義します。 MBCS でビルドするには、シンボル `_MBCS` を定義します。 Unicode をビルドするには、`_UNICODE`記号 を定義します。 1 バイト アプリケーションをビルドする場合は、どちらも定義しません (既定)。 MFC アプリケーションでは、既定で `_UNICODE` が定義されています。

データ`_TCHAR`型は、tchar.h で条件付きで定義されます。 シンボル`_UNICODE`がビルドに定義されている場合は`_TCHAR`**、wchar_t**として定義されます。それ以外の場合は、シングルバイトビルドおよび MBCS ビルドの場合は char**として定義**されます。 (**wchar_t**は、Unicode ワイド文字の基本データ型で、8 ビット符号**付き char**に対応する 16 ビットのデータ型です)。国際化アプリケーションの場合は`_tcs`、バイトではなく単位で動作する`_TCHAR`関数ファミリを使用します。 たとえば、`_tcsncpy`バイトではなく`n``_TCHARs``n`コピーをコピーします。

1 バイト文字セット (SBCS: Single Byte Character Set) の文字列処理関数の中には、符号付きの `char*` パラメーターを受け取るものがあります。このため、`_MBCS` を定義すると、型の不一致を知らせるコンパイラの警告が生成される場合があります。 この警告を回避する方法は 3 つあります。

1. タイプ セーフなインライン関数サンクは、tchar.h で使用します。 これは既定の動作です。

1. コマンド行で定義して、tchar.h`_MB_MAP_DIRECT`の直接マクロを使用します。 この場合は、型を手作業で一致させる必要があります。 これは一番速い方法ですが、タイプ セーフではありません。

1. タイプ セーフな静的にリンクされたライブラリ関数を tchar.h で使用します。 この場合は、コマンド ラインで定数 `_NO_INLINING` を定義します。 これは、一番時間がかかりますが、一番タイプ セーフな方法です。

### <a name="preprocessor-directives-for-generic-text-mappings"></a>汎用テキスト マッピング用のプリプロセッサ ディレクティブ

|#define|コンパイル後の状態|例|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode (ワイド文字)|`_tcsrev` は `_wcsrev` に割り当てられます。|
|`_MBCS`|マルチバイト文字|`_tcsrev` は `_mbsrev` に割り当てられます。|
|なし (既定では `_UNICODE` も `_MBCS` も未定義)|SBCS (ASCII)|`_tcsrev` は `strrev` に割り当てられます。|

たとえば、 tchar.h`_tcsrev`で定義されている汎用テキスト関数は、 プログラムで定義`_mbsrev``_MBCS`した場合、または 定義されている場合に`_wcsrev`マップされます`_UNICODE`。 それ以外の場合、`_tcsrev` は `strrev` に割り当てられます。 その他のデータ型のマッピングは、プログラミングの便宜のために tchar.h で提供されていますが`_TCHAR`、最も便利です。

### <a name="generic-text-data-type-mappings"></a>汎用テキストのデータ型のマップ

|汎用テキスト<br /> データ型名|_UNICODE &<br /> _MBCS が未定義の場合|_MBCS<br /> 定義済み|_UNICODE<br /> 定義済み|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**char**|**char**|**wchar_t**|
|`_TINT`|**int**|**unsigned int**|`wint_t`|
|`_TSCHAR`|**signed char**|**signed char**|**wchar_t**|
|`_TUCHAR`|**unsigned char**|**unsigned char**|**wchar_t**|
|`_TXCHAR`|**char**|**unsigned char**|**wchar_t**|
|`_T` または `_TEXT`|影響なし (プリプロセッサによって削除される)|影響なし (プリプロセッサによって削除される)|`L`(次の文字または文字列を対応する Unicode に変換します)|

ルーチン、変数、およびその他のオブジェクトの汎用テキストマッピングのリストについては、『ランタイム・ライブラリー [・リファレンス』の「汎用テキスト・マッピング](../c-runtime-library/generic-text-mappings.md)」を参照してください。

> [!NOTE]
> Unicode の文字列には NULL バイトが含まれている可能性があるため、この文字列と一緒に `str` ファミリの関数を使用しないでください。 同様に、MBCS (または SBCS) 文字列には `wcs` ファミリの関数を使用しないでください。

MBCS、Unicode、および SBCS の各モデルにマッピングするために、`_TCHAR` と `_tcsrev` を使用するコード例を次に示します。

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

`_MBCS` が定義されていると、プリプロセッサによって次のコードに変換されます。

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

`_UNICODE` が定義されていると、プリプロセッサによって次のコードに変換されます。

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

定義`_MBCS``_UNICODE`されていない場合、プリプロセッサはフラグメントを 1 バイト ASCII コードにマップします。

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

このように、1 つのソース コード ファイルを記述、保守、およびコンパイルすることで、3 種類のそれぞれの文字セットに固有のルーチンを実行できます。

## <a name="see-also"></a>関連項目

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)<br/>
[_MBCS コードでの TCHAR.H データ型の使用](../text/using-tchar-h-data-types-with-mbcs-code.md)
