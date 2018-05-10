---
title: _setmbcp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _setmbcp
apilocation:
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
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs:
- C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91993171def417adfc389420d1376e5a71f8cda0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="setmbcp"></a>_setmbcp

新しいマルチバイト コード ページを設定します。

## <a name="syntax"></a>構文

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>パラメーター

*コード ページ*<br/>
ロケールに依存しないマルチバイトのルーチンのための新しいコード ページ設定。

## <a name="return-value"></a>戻り値

コード ページが正常に設定されている場合は、0 を返します。 無効なコード ページの値が指定した場合*コードページ*-1 とコード ページの設定は変更を返します。 セット**errno**に**EINVAL**メモリ割り当てエラーが発生した場合。

## <a name="remarks"></a>コメント

**_Setmbcp**関数は新しいマルチバイト コード ページを指定します。 既定では、ランタイム システムはマルチバイト コード ページを、システムの既定の ANSI コード ページに自動的に設定します。 マルチバイト コード ページの設定は、ロケールに依存していないすべてのマルチバイトのルーチンに影響します。 ただし、可能であればに指示する **_setmbcp**現在のロケールに対して定義されているコード ページを使用する (次のマニフェスト定数の一覧を参照してくださいおよび関連する動作)。 マルチバイト コード ページではなく、ロケールのコード ページに依存しているマルチバイトのルーチンの一覧については、「[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)」を参照してください。

マルチバイト コード ページは、次のランタイム ライブラリ ルーチンによる、マルチバイト文字の処理にも影響します。

||||
|-|-|-|
|[_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

さらに、マルチバイト文字が表示されるすべてのランタイム ライブラリ ルーチン*argv*または*envp*プログラムのパラメーターと引数 (など、 **_exec**と **_spawn**ファミリ) これらの文字列のマルチバイト コード ページに従って処理します。 したがって、これらのルーチンがへの呼び出しによって影響をも **_setmbcp**マルチバイト コード ページを変更します。

*コードページ*引数は、次の値のいずれかに設定することができます。

- **_MB_CP_ANSI**を使用して ANSI コード ページは、プログラムの起動時にオペレーティング システムから取得します。

- **_MB_CP_LOCALE**前の呼び出しから取得した現在のロケールのコード ページを使用して[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。

- **_MB_CP_OEM**使用の OEM コード ページは、プログラムの起動時にオペレーティング システムから取得します。

- **_MB_CP_SBCS** 1 バイト コード ページを使用します。 コード ページを設定すると **_MB_CP_SBCS**など、日常的な[_ismbblead](ismbblead-ismbblead-l.md)常に false を返します。

- 他の任意の有効なコード ページ値。値は、ANSI、OEM、またはその他のオペレーティング システムがサポートするコード ページであるかに関係ありません。ただし、サポートされていない UTF-7 と UTF-8 は除きます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_getmbcp](getmbcp.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
