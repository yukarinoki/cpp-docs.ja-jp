---
title: _setmaxstdio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 785fcc05c6b19086c14edc85983749894c867c18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407669"
---
# <a name="setmaxstdio"></a>_setmaxstdio

同時に開いているファイルの数の最大値の設定、 **stdio**レベル。

## <a name="syntax"></a>構文

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>パラメーター

*newmax*<br/>
同時に開いているファイルの数の新しい最大値、 **stdio**レベル。

## <a name="return-value"></a>戻り値

返します*newmax*正常終了した場合は-1 をそれ以外の場合。

場合*newmax*はより小さい **_IOB_ENTRIES**以上」の説明に従って、オペレーティング システム、無効なパラメーター ハンドラーで使用できるハンドルの最大数が起動し、 [パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の続行には、この関数は-1 を返しセットが許可された場合**errno**に**EINVAL**です。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_Setmaxstdio**関数で同時に開いているファイルの数の最大値を変更する、 **stdio**レベル。

C ランタイム I/O では、Win32 プラットフォームで、以前のバージョンよりも多くの開いているファイルをサポートするようになりました。 最大で 2,048 のファイルが同時に開くことができる、 [lowio レベル](../../c-runtime-library/low-level-i-o.md)(つまり、開かれ、してアクセス、 **_open**、**読む (_r)**、 **_write**、I/O 関数のファミリなど)。 最大で 512 ファイルが同時に開くことができる、 [stdio レベル](../../c-runtime-library/stream-i-o.md)(つまり、開かれ、してアクセス、 **fopen**、 **fgetc**、 **fputc**、関数のファミリなど)。 512 の開いているファイルの制限、 **stdio**により 2,048 の最大レベルを増やすことができます、 **_setmaxstdio**関数。

**Stdio**-レベルなどの関数、 **fopen**の上に構築された、 **lowio**関数、2,048 の最大値は、数の上限に同時にC ランタイム ライブラリからアクセスされたファイルを開きます。

> [!NOTE]
> この上限は、特定の Win32 プラットフォームと構成でサポートされる上限を超える可能性があります。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

参照してください[_getmaxstdio](getmaxstdio.md)の使用例については **_setmaxstdio**です。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
