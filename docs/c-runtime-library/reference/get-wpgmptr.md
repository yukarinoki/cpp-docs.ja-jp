---
title: _get_wpgmptr
ms.date: 4/2/2020
api_name:
- _get_wpgmptr
- _o__get_wpgmptr
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_wpgmptr
- _get_wpgmptr
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
ms.openlocfilehash: 1e54d3dbdc837c491f5b39d33a9b8197094ac60b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344862"
---
# <a name="_get_wpgmptr"></a>_get_wpgmptr

**_wpgmptr**グローバル変数の現在の値を取得します。

## <a name="syntax"></a>構文

```C
errno_t _get_wpgmptr(
   wchar_t **pValue
);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
**_wpgmptr**変数の現在の値を格納する文字列へのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 *pValue*が**NULL**の場合は、「パラメータ[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメータ ハンドラが呼び出されます。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

## <a name="remarks"></a>解説

プログラムに**wmain() や wWinMain()** などの幅の**wWinMain()** 広いエントリポイントがある場合にのみ **、_get_wpgmptr**を呼び出します。 **_wpgmptr**グローバル変数には、ワイド文字ストリングとしてプロセスに関連付けられた実行可能ファイルへの完全パスが含まれます。 詳細については、「[_pgmptr、_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_get_pgmptr](get-pgmptr.md)<br/>
