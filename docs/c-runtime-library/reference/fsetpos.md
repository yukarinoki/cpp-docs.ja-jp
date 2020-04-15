---
title: fsetpos
ms.date: 4/2/2020
api_name:
- fsetpos
- _o_fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 22b8cebd0154c0dbfc3d21843380ebc9a139059a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345716"
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

成功した場合 **、fsetpos は**0 を返します。 失敗した場合、関数は 0 以外の値を返し **、errno**を次のマニフェスト定数 (ERRNO で定義) のいずれかに設定します。H): **EBADF**は、ファイルがアクセス不能であるか、*ストリーム*が指すオブジェクトが有効なファイル構造ではないことを意味します。または**EINVAL**は *、ストリーム*または*pos*に無効な値が渡されたことを意味します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**fsetpos**関数は *、ストリーム*のファイル位置インジケーターを*pos*の**値に設定***します。* この関数は、ファイルの終わりインジケーターをクリアし、*ストリーム*に[対する ungetc](ungetc-ungetwc.md)の影響を元に消します。 **fsetpos**を呼び出した後、*ストリーム*の次の操作は入力または出力のいずれかになります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[fgetpos](fgetpos.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
