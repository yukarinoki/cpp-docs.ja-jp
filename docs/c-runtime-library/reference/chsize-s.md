---
title: _chsize_s
ms.date: 4/2/2020
api_name:
- _chsize_s
- _o__chsize_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: 70845124eb889d73a0f87aadd923e2d86db96c29
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350078"
---
# <a name="_chsize_s"></a>_chsize_s

ファイル サイズを変更します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_chsize](chsize.md) です。

## <a name="syntax"></a>構文

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
開いているファイルを参照するファイル記述子。

*サイズ*<br/>
バイト単位のファイルの新しい長さ。

## <a name="return-value"></a>戻り値

**ファイル**サイズが正常に変更された場合は、値 0 が返_chsize_s。 ゼロ以外の戻り値はエラーを示します: 指定されたファイルがアクセスに対してロックされている場合は**EACCES、** 指定されたファイルが読み取り専用または記述子が無効な場合は**EBADF、** 装置にスペースが残っていない場合は**ENOSPC、** サイズが 0 未満の場合は**EINVAL**です。 **errno**は同じ値に設定されます。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_chsize_s**関数は *、fd*に関連付けられたファイルを*size*で指定された長さに拡張または切り捨てます。 ファイルは、書き込みを許可するモードで開かれている必要があります。 ファイルが拡張される場合は、null 文字 ('\0') が追加されます。 ファイルが切り捨てられる場合、短くなったファイルの末尾からファイルの元の長さまでのすべてのデータは失われます。

**_chsize_s**はファイル サイズとして 64 ビット整数を使用するため、4 GB を超えるファイル サイズを処理できます。 **_chsize**は、32 ビットのファイル サイズに制限されています。

この関数は、パラメーターを検証します。 *fd*が有効なファイル記述子でない場合、または size がゼロ未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター・ハンドラーが呼び出されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
