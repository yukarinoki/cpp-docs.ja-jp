---
title: Tchar.h における汎用テキスト マッピング |Microsoft Docs
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5959e026df9fcffc3295000b3d433aab16100fb6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375302"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar.h における汎用テキストのマッピング

国際対応のコードの転送を簡略化するのには、Microsoft ランタイム ライブラリは、多くのデータ型、ルーチン、およびその他のオブジェクトの Microsoft 固有の汎用テキスト マッピングを提供します。 1 バイト、マルチバイト、コンパイルできるジェネリック コードを記述する、Tchar.h で定義されているこれらのマッピングを使用するかを使用して定義するマニフェスト定数に応じて、Unicode 文字のセットを`#define`ステートメント。 汎用テキスト マッピングは Microsoft 固有の拡張機能であり、ANSI とは互換性がありません。

Tchar.h を使用すると、1 バイト、マルチバイト文字のセット (MBCS) と同じソースから Unicode アプリケーションを構築できます。 Tchar.h では、プレフィックス `_tcs` の付いたマクロが定義されており、正しいプリプロセッサ定義に応じて `str`、`_mbs`、`wcs` のいずれかの関数に割り当てられます。 MBCS でビルドするには、シンボル `_MBCS` を定義します。 Unicode をビルドするには、シンボルを定義`_UNICODE`します。 1 バイト アプリケーションをビルドする場合は、どちらも定義しません (既定)。 MFC アプリケーションでは、既定で `_MBCS` が定義されています。

`_TCHAR` データ型は、Tchar.h で条件に応じて定義されます。 場合、シンボル`_UNICODE`、ビルドが定義されている`_TCHAR`として定義されます**wchar_t**。 そうしないと、1 バイト、MBCS のビルドとして定義されて**char**します。 (**wchar_t**、基本の Unicode ワイド文字データ型を 8 ビット符号付き 16 ビット版は、 **char**)。国際対応のアプリケーションでは、バイトではなく `_tcs` を扱う `_TCHAR` ファミリの関数を使う必要があります。 たとえば、`_tcsncpy`コピー `n` `_TCHARs`ではなく、`n`バイト。

1 バイト文字セット (SBCS: Single Byte Character Set) の文字列処理関数の中には、符号付きの `char*` パラメーターを受け取るものがあります。このため、`_MBCS` を定義すると、型の不一致を知らせるコンパイラの警告が生成される場合があります。 この警告を回避する方法は 3 つあります。

1. Tchar.h のタイプ セーフなインライン関数サンクを使用します。 これが既定の動作です。

1. コマンド ラインで `_MB_MAP_DIRECT` を定義して、Tchar.h の直接マクロを使用します。 この場合は、型を手作業で一致させる必要があります。 これは一番速い方法ですが、タイプ セーフではありません。

1. Tchar.h のタイプ セーフな静的リンク ライブラリ関数のサンクを使用します。 この場合は、コマンド ラインで定数 `_NO_INLINING` を定義します。 これは、一番時間がかかりますが、一番タイプ セーフな方法です。

### <a name="preprocessor-directives-for-generic-text-mappings"></a>汎用テキスト マッピング用のプリプロセッサ ディレクティブ

|#define|コンパイル後の状態|例|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode (ワイド文字)|`_tcsrev` は `_wcsrev` に割り当てられます。|
|`_MBCS`|マルチバイト文字|`_tcsrev` は `_mbsrev` に割り当てられます。|
|なし (既定では `_UNICODE` も `_MBCS` も未定義)|SBCS (ASCII)|`_tcsrev` は `strrev` に割り当てられます。|

たとえば、Tchar.h で定義されている汎用テキスト関数 `_tcsrev` は、プログラムで `_mbsrev` が定義されていると `_MBCS` になり、`_wcsrev` が定義されていると `_UNICODE` になります。 それ以外の場合、`_tcsrev` は `strrev` に割り当てられます。 プログラミングに便利なように他のデータ型のマッピングも Tchar.h に用意されていますが、`_TCHAR` が最も多く使用されます。

### <a name="generic-text-data-type-mappings"></a>汎用テキストのデータ型のマップ

|汎用テキスト<br /> データ型名|_UNICODE &<br /> _MBCS が未定義の場合|_MBCS<br /> 定義済み|_UNICODE<br /> 定義済み|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**char**|**char**|**wchar_t**|
|`_TINT`|**int**|**unsigned int**|`wint_t`|
|`_TSCHAR`|**符号付き文字**|**符号付き文字**|**wchar_t**|
|`_TUCHAR`|**unsigned char**|**unsigned char**|**wchar_t**|
|`_TXCHAR`|**char**|**unsigned char**|**wchar_t**|
|`_T` または `_TEXT`|影響なし (プリプロセッサによって削除される)|影響なし (プリプロセッサによって削除される)|`L` (次の文字または文字列を対応する Unicode に変換)|

ルーチン、変数、およびその他のオブジェクトの汎用テキスト マッピングの一覧は、次を参照してください。[汎用テキスト マッピング](../c-runtime-library/generic-text-mappings.md)ランタイム ライブラリのリファレンス。

> [!NOTE]
>  Unicode の文字列には NULL バイトが含まれている可能性があるため、この文字列と一緒に `str` ファミリの関数を使用しないでください。 同様に、MBCS (または SBCS) 文字列には `wcs` ファミリの関数を使用しないでください。

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

どちらの場合`_MBCS`も`_UNICODE`されている、定義されている、プリプロセッサによってマップされます、フラグメント 1 バイトの ASCII コードに次のようにします。

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

このように、1 つのソース コード ファイルを記述、保守、およびコンパイルすることで、3 種類のそれぞれの文字セットに固有のルーチンを実行できます。

## <a name="see-also"></a>関連項目

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)<br/>
[_MBCS コードでの TCHAR.H データ型の使用](../text/using-tchar-h-data-types-with-mbcs-code.md)