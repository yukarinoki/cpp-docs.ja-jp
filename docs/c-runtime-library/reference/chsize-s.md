---
description: '詳細については、次を参照してください: _chsize_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b3fa28923b558dc9b396cffc3418ff679349000d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253092"
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

*スクリプター*<br/>
開いているファイルを参照するファイル記述子。

*size*<br/>
バイト単位のファイルの新しい長さ。

## <a name="return-value"></a>戻り値

ファイルサイズが正常に変更された場合、 **_chsize_s** は値0を返します。 0以外の戻り値は、エラーを示します。指定されたファイルがアクセスに対してロックされている場合、 **EACCES** は、指定されたファイルが読み取り専用である場合、または、記述子が無効な場合は ENOSPC **、デバイス** に領域がない場合は 、サイズが0未満の場合は **EINVAL** を返します。 **errno** が同じ値に設定されています。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Chsize_s** 関数は、 *fd* に関連付けられているファイルを *size* によって指定された長さに拡張または切り捨てます。 ファイルは、書き込みを許可するモードで開かれている必要があります。 ファイルが拡張される場合は、null 文字 ('\0') が追加されます。 ファイルが切り捨てられる場合、短くなったファイルの末尾からファイルの元の長さまでのすべてのデータは失われます。

**_chsize_s** は、ファイルサイズとして64ビット整数を受け取るため、4 GB を超えるファイルサイズを処理できます。 **_chsize** は、32ビットのファイルサイズに制限されています。

この関数は、パラメーターを検証します。 *Fd* が有効なファイル記述子でないか、またはサイズが0未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
