---
title: fsetpos
ms.date: 11/04/2016
apiname:
- fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 9854c71e381da6ec9a75d440b9588e2476bada7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528233"
---
# <a name="fsetpos"></a>fsetpos

ストリームの位置インジケーターを設定します。

## <a name="syntax"></a>構文

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*pos*<br/>
位置インジケーターのストレージ。

## <a name="return-value"></a>戻り値

成功した場合、 **fsetpos** 0 を返します。 失敗した場合は、関数は 0 以外の値を返します。 設定および**errno** 、次のいずれかのマニフェスト定数 (ERRNO で定義されています。H): **EBADF**、ファイルにアクセスできないことを意味するか、オブジェクトを*ストリーム*へのポインターでない有効なファイル構造体または**EINVAL**、つまり、値が無効です*ストリーム*または*pos*が渡されました。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Fsetpos**関数のファイル位置インジケーターを設定する*ストリーム*の値に*pos*が、前回の呼び出しで取得される**fgetpos**に対して*ストリーム*します。 この関数は、ファイルの終わりインジケーターをクリアしのすべての効果を元に戻します[ungetc](ungetc-ungetwc.md)で*ストリーム*します。 呼び出した後**fsetpos**の次の操作*ストリーム*するか、入力または出力可能性があります。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[fgetpos](fgetpos.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
