---
title: 汎用テキスト マップの使用
description: C ランタイムにおけるデータ型、ルーチン、およびその他のオブジェクトに対する Microsoft 固有のマッピングの概要です。
ms.topic: conceptual
ms.date: 11/04/2016
f1_keywords:
- _UNICODE
helpviewer_keywords:
- _TXCHAR type
- TINT type
- _TCHAR type
- TSCHAR type
- TEXT type
- TCHAR type
- TCHAR.H data types, mappings defined in
- generic-text data types
- _TINT type
- TUCHAR type
- _UNICODE constant
- TXCHAR type
- generic-text mappings
- _TSCHAR type
- T type
- mappings, generic-text
- _TUCHAR type
- MBCS data type
- _MBCS data type
- _TEXT type
- UNICODE constant
- _T type
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
ms.openlocfilehash: ea3b1eef413a0d9f52e81795c04424d533b83504
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590109"
---
# <a name="using-generic-text-mappings"></a>汎用テキスト マップの使用

**Microsoft 固有の仕様**

さまざまな国際市場に対応したコード開発を容易にするために、Microsoft ランタイム ライブラリには、多くのデータ型やルーチン、オブジェクトなどで利用できる Microsoft 固有の "汎用テキスト" マップが用意されています。 これらのマップは、TCHAR.H で定義されています。 これらの名前のマップを使用して、`#define` ステートメントを使用して定義するマニフェスト定数に応じて ASCII (SBCS)、MBCS、Unicode という 3 種類の文字セットのいずれかにコンパイルされるジェネリック コードを書き込むことができます。 汎用テキスト マッピングは Microsoft 固有の拡張機能であり、ANSI とは互換性がありません。

### <a name="preprocessor-directives-for-generic-text-mappings"></a>汎用テキスト マッピング用のプリプロセッサ ディレクティブ

|#define|コンパイル後の状態|例|
|--------------|----------------------|-------------|
|`_UNICODE`|Unicode (ワイド文字)|`_tcsrev` は `_wcsrev` にマップされます。|
|`_MBCS`|マルチバイト文字|`_tcsrev` は `_mbsrev` にマップされます。|
|なし (既定では `_UNICODE` も `_MBCS` も未定義)|SBCS (ASCII)|`_tcsrev` は `strrev` にマップされます。|

たとえば、TCHAR.H で定義した汎用テキスト関数 `_tcsrev` は、プログラムで `MBCS` を定義した場合には `mbsrev` にマップされ、`_UNICODE` を定義した場合には `_wcsrev` にマップされます。 それ以外の場合、`_tcsrev` は `strrev` にマップされます。

汎用テキストデータ型 `_TCHAR` 。 TCHAR でも定義されています。H は、が定義されている場合は型にマップされ、が定義されている場合は型に、 **`char`** `_MBCS` どちらの **`wchar_t`** `_UNICODE` **`char`** 定数も定義されていない場合はを入力します。 プログラミングに便利なように、TCHAR.H には他のデータ型のマッピングも用意されていますが、`_TCHAR` が最も使いやすいデータ型です。

### <a name="generic-text-data-type-mappings"></a>汎用テキストのデータ型のマップ

|汎用テキストのデータ型の名前|SBCS (_UNICODE、_MBCS が未定義の場合)|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TCHAR`|**`char`**|**`char`**|**`wchar_t`**|
|`_TINT`|**`int`**|**`int`**|`wint_t`|
|`_TSCHAR`|**`signed char`**|**`signed char`**|**`wchar_t`**|
|`_TUCHAR`|**`unsigned char`**|**`unsigned char`**|**`wchar_t`**|
|`_TXCHAR`|**`char`**|**`unsigned char`**|**`wchar_t`**|
|`_T` または `_TEXT`|影響なし (プリプロセッサによって削除される)|影響なし (プリプロセッサによって削除される)|`L` (後続の文字または文字列を対応する Unicode の文字または文字列に変換する)|

ルーチンや変数などのオブジェクトの汎用テキスト マップの詳細な一覧については、「[汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)」をご覧ください。

MBCS、Unicode、および SBCS の各モデルにマッピングするために、`_TCHAR` と `_tcsrev` を使用するコード例を次に示します。

```
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

`MBCS` を定義した場合は、プリプロセッサによって上述のコードが次のコードにマップされます。

```
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

`_UNICODE` を定義した場合は、プリプロセッサによって同じコードが次のコードにマップされます。

```
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

`_MBCS` と `_UNICODE` のどちらも定義しなかった場合は、プリプロセッサによって同様のコードが次のような 1 バイトの ASCII コードにマップされます。

```
char *RetVal, *szString;
RetVal = strrev(szString);
```

このように、1 つのソース コード ファイルを記述、保守、コンパイルすることで、3 種類のそれぞれの文字セットに固有のルーチンを実行できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[汎用テキストマッピング](../c-runtime-library/generic-text-mappings.md)<br/>
[データ型のマッピング](../c-runtime-library/data-type-mappings.md)<br/>
[定数とグローバル変数のマッピング](../c-runtime-library/constant-and-global-variable-mappings.md)<br/>
[ルーチンのマッピング](../c-runtime-library/routine-mappings.md)<br/>
[汎用テキストプログラムのサンプル](../c-runtime-library/a-sample-generic-text-program.md)
