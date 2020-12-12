---
description: '詳細情報: fsetpos'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: e8259bcf4dba951bf6603fb5d4984db6ece0e266
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114222"
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

*一連*<br/>
**FILE** 構造体へのポインター。

*pos*<br/>
位置インジケーターのストレージ。

## <a name="return-value"></a>戻り値

成功した場合、 **fsetpos** は0を返します。 エラーが発生した場合、関数は0以外の値を返し、 **errno** に次のマニフェスト定数のいずれかを設定します (errno に定義されています)。H): **EBADF**。ファイルにアクセスできないこと、または *ストリーム* が指すオブジェクトが有効なファイル構造ではないことを意味します。または **EINVAL**。 *ストリーム* または *pos* の無効な値が渡されたことを意味します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**Fsetpos** 関数は *、ストリームの* ファイル位置インジケーターを *pos* の値に設定します。これは、*ストリーム* に対して **fgetpos** を呼び出す前の呼び出しで取得されます。 関数は、ファイルの終端のインジケーターをクリアし、*ストリーム* で [ungetc](ungetc-ungetwc.md)のすべての効果を元に戻します。 **Fsetpos** を呼び出した後、*ストリーム* に対する次の操作は、入力または出力のいずれかになります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[fgetpos](fgetpos.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
