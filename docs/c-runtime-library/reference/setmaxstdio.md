---
title: _setmaxstdio
ms.date: 11/04/2016
apiname:
- _setmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setmaxstdio
- _setmaxstdio
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
ms.openlocfilehash: 58cffedf673e23a69c2d8040071b2e3353ff4502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356343"
---
# <a name="setmaxstdio"></a>_setmaxstdio

同時に開かれるファイルの数の最大値の設定、 **stdio**レベル。

## <a name="syntax"></a>構文

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>パラメーター

*newmax*<br/>
同時に開かれるファイルの数の新しい最大値、 **stdio**レベル。

## <a name="return-value"></a>戻り値

返します*newmax*成功した場合はそれ以外の場合は-1。

場合*newmax*がより小さい **_IOB_ENTRIES** 」の説明に従って、オペレーティング システム、無効なパラメーター ハンドラーで使用できるハンドルの最大数が呼び出されるより大きいまたは[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行が続行すると、この関数は-1 を返し、セットを許可された場合**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**_Setmaxstdio**関数で同時に開かれるファイルの数の最大値を変更する、 **stdio**レベル。

C ランタイム I/O では、Win32 プラットフォームで、以前のバージョンよりも多くの開いているファイルをサポートするようになりました。 最大で 2,048 ファイルで同時に開くことができます、 [lowio レベル](../../c-runtime-library/low-level-i-o.md)(つまり、開かれ、してアクセス、**開く (_o)**、 **_read**、 **_write**の I/O 関数ファミリなど)。 最大で 512 ファイルで同時に開くことができます、 [stdio レベル](../../c-runtime-library/stream-i-o.md)(つまり、開かれのアクセス、 **fopen**、 **fgetc**、 **fputc**、関数のファミリなど)。 512 の開いているファイルでの制限、 **stdio**で 2,048 の最大レベルを上げることができます、 **_setmaxstdio**関数。

**Stdio**-レベルなどの関数**fopen**の上に構築された、 **lowio**関数、2,048 の最大値は、数の上限に同時にC ランタイム ライブラリによってアクセスされるファイルを開きます。

> [!NOTE]
> この上限は、特定の Win32 プラットフォームと構成でサポートされる上限を超える可能性があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

参照してください[_getmaxstdio](getmaxstdio.md)の使用例については **_setmaxstdio**します。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
