---
title: _setmbcp
ms.date: 4/2/2020
api_name:
- _setmbcp
- _o__setmbcp
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: 61086471c6194aaa8434d291647978bf891a8aea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337603"
---
# <a name="_setmbcp"></a>_setmbcp

新しいマルチバイト コード ページを設定します。

## <a name="syntax"></a>構文

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>パラメーター

*コードページ*<br/>
ロケールに依存しないマルチバイトのルーチンのための新しいコード ページ設定。

## <a name="return-value"></a>戻り値

コード ページが正常に設定されている場合は、0 を返します。 *コード ページ*に無効なコード ページ値が指定されている場合は、-1 が返され、コード ページ設定は変更されません。 メモリ割り当てエラーが発生した場合に**errno**を**EINVAL**に設定します。

## <a name="remarks"></a>解説

**_setmbcp**関数は、新しいマルチバイト・コード・ページを指定します。 既定では、ランタイム システムはマルチバイト コード ページを、システムの既定の ANSI コード ページに自動的に設定します。 マルチバイト コード ページの設定は、ロケールに依存していないすべてのマルチバイトのルーチンに影響します。 ただし、現在のロケールに対して定義されているコード ページを使用するように **_setmbcp**に指示することはできます (次のマニフェスト定数と関連する動作結果の一覧を参照してください)。 マルチバイト コード ページではなく、ロケールのコード ページに依存しているマルチバイトのルーチンの一覧については、「[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)」を参照してください。

マルチバイト コード ページは、次のランタイム ライブラリ ルーチンによる、マルチバイト文字の処理にも影響します。

||||
|-|-|-|
|[_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

さらに、マルチバイト文字*argv*または*envp*プログラム引数をパラメーターとして受け取るランタイム ライブラリ ルーチン **(_exec**や **_spawn**ファミリなど) は、マルチバイト コード ページに従ってこれらの文字列を処理します。 したがって、これらのルーチンは、マルチバイト・コード・ページを変更する **_setmbcp**の呼び出しによっても影響を受けます。

*コードページ*引数は、次のいずれかの値に設定できます。

- **_MB_CP_ANSI**プログラムの起動時にオペレーティング システムから取得した ANSI コード ページを使用します。

- **_MB_CP_LOCALE**前の呼び出しから取得した現在のロケールのコード ページを使用して[setlocale](setlocale-wsetlocale.md)を指定します。

- **_MB_CP_OEM**プログラムの起動時にオペレーティング システムから取得した OEM コード ページを使用します。

- **_MB_CP_SBCS**1 バイトのコード ページを使用します。 コード ページが **_MB_CP_SBCS**に設定されている場合[、_ismbblead](ismbblead-ismbblead-l.md)などのルーチンは常に false を返します。

- **_MB_CP_UTF8**UTF-8 を使用します。  コード ページが **_MB_CP_UTF8**に設定されている場合[、_ismbblead](ismbblead-ismbblead-l.md)などのルーチンは常に false を返します。

- その他の有効なコード ページ値は、値が ANSI、OEM、またはその他のオペレーティング システムでサポートされるコード ページ (サポートされていない UTF-7 を除く) であるかどうかに関係なく、任意の値です。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_getmbcp](getmbcp.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
