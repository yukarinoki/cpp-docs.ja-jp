---
description: 詳細については、「tchar.h での Generic-Text のマッピング」を参照してください。
title: Tchar. h での Generic-Text のマッピング
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
ms.openlocfilehash: f083dc03eab7db25b54955d8d34a13f2b5b7197b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118349"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar. h での Generic-Text のマッピング

国際対応のコードの転送を簡単にするために、Microsoft ランタイムライブラリでは、多くのデータ型、ルーチン、およびその他のオブジェクトに対して、Microsoft 固有の汎用テキストマッピングが提供されています。 Tchar.h で定義されているこれらのマッピングを使用すると、ステートメントを使用して定義したマニフェスト定数に応じて、1バイト、マルチバイト、または Unicode 文字セットに対してコンパイルできる汎用コードを記述できます `#define` 。 汎用テキスト マッピングは Microsoft 固有の拡張機能であり、ANSI とは互換性がありません。

Tchar.h を使用すると、1バイト、マルチバイト文字セット (MBCS)、および Unicode アプリケーションを同じソースから作成できます。 tchar.h は、正しいプリプロセッサ定義を持つマクロ (プレフィックスを持つ) を定義し、 `_tcs` 必要に `str` `_mbs` 応じて、、または関数にマップします `wcs` 。 MBCS でビルドするには、シンボル `_MBCS` を定義します。 Unicode を作成するには、シンボルを定義し `_UNICODE` ます。 1 バイト アプリケーションをビルドする場合は、どちらも定義しません (既定)。 MFC アプリケーションでは、既定で `_UNICODE` が定義されています。

`_TCHAR`データ型は、tchar. h で条件付きで定義されます。 シンボル `_UNICODE` がビルドに対して定義されている場合、 `_TCHAR` はとして定義されます **`wchar_t`** 。それ以外の場合、1バイトビルドと MBCS ビルドではとして定義され **`char`** ます。 (は **`wchar_t`** 、Unicode ワイド文字の基本データ型で、8ビットに相当する16ビット **`signed char`** です)。国際対応アプリケーションの場合は、 `_tcs` バイトではなく単位で動作するファミリの関数を使用し `_TCHAR` ます。 たとえば、は `_tcsncpy` バイトではなくをコピーし `n` `_TCHARs` `n` ます。

一部の1バイト文字セット (SBCS) の文字列処理関数は (符号付き) **`char*`** パラメーターを受け取るため、が定義されている場合、型が一致しないとコンパイラの警告結果が返され `_MBCS` ます。 この警告を回避する方法は 3 つあります。

1. Tchar.h のタイプセーフなインライン関数サンクを使用します。 これが既定の動作です。

1. コマンドラインでを定義して、tchar.h の直接マクロを使用します `_MB_MAP_DIRECT` 。 この場合は、型を手作業で一致させる必要があります。 これは一番速い方法ですが、タイプ セーフではありません。

1. Tchar.h のタイプセーフな静的リンクライブラリ関数サンクを使用します。 この場合は、コマンド ラインで定数 `_NO_INLINING` を定義します。 これは、一番時間がかかりますが、一番タイプ セーフな方法です。

### <a name="preprocessor-directives-for-generic-text-mappings"></a>汎用テキスト マッピング用のプリプロセッサ ディレクティブ

|#define|コンパイル後の状態|例|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode (ワイド文字)|`_tcsrev` は `_wcsrev` にマップされます。|
|`_MBCS`|マルチバイト文字|`_tcsrev` は `_mbsrev` にマップされます。|
|なし (既定では `_UNICODE` も `_MBCS` も未定義)|SBCS (ASCII)|`_tcsrev` は `strrev` にマップされます。|

たとえば、tchar.h で定義されている汎用テキスト関数は、 `_tcsrev` プログラムでを定義した場合はにマップされ、を定義した場合はにマップされ `_mbsrev` `_MBCS` `_wcsrev` `_UNICODE` ます。 それ以外の場合、`_tcsrev` は `strrev` に割り当てられます。 その他のデータ型のマッピングは、プログラミングの利便性を高めるために tchar.h に用意されていますが、 `_TCHAR` 最も役に立ちます。

### <a name="generic-text-data-type-mappings"></a>汎用テキストのデータ型のマップ

|汎用テキスト<br /> データ型名|_UNICODE &<br /> _MBCS が未定義の場合|_MBCS<br /> 定義済み|_UNICODE<br /> 定義済み|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**`char`**|**`char`**|**`wchar_t`**|
|`_TINT`|**`int`**|**`unsigned int`**|`wint_t`|
|`_TSCHAR`|**`signed char`**|**`signed char`**|**`wchar_t`**|
|`_TUCHAR`|**`unsigned char`**|**`unsigned char`**|**`wchar_t`**|
|`_TXCHAR`|**`char`**|**`unsigned char`**|**`wchar_t`**|
|`_T` または `_TEXT`|影響なし (プリプロセッサによって削除される)|影響なし (プリプロセッサによって削除される)|`L` (次の文字または文字列を Unicode 対応の文字列に変換します)|

ルーチン、変数、およびその他のオブジェクトの汎用テキストマッピングの一覧については、Run-Time ライブラリリファレンスの「 [汎用テキストマップ](../c-runtime-library/generic-text-mappings.md) 」を参照してください。

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

`_MBCS` `_UNICODE` とがどちらも定義されていない場合、プリプロセッサは次のようにフラグメントを1バイトの ASCII コードにマップします。

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

このように、1 つのソース コード ファイルを記述、保守、およびコンパイルすることで、3 種類のそれぞれの文字セットに固有のルーチンを実行できます。

## <a name="see-also"></a>関連項目

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)<br/>
[TCHAR を使用します。_MBCS コードを使用した H データ型](../text/using-tchar-h-data-types-with-mbcs-code.md)
