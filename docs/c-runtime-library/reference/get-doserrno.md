---
title: _get_doserrno | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_doserrno
- get_doserrno
dev_langs:
- C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7cef2c068fad2f18cb1d11d33e551588800cb64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399570"
---
# <a name="getdoserrno"></a>_get_doserrno

変換する前に、オペレーティング システムによって返されるエラー値を取得、 **errno**値。

## <a name="syntax"></a>構文

```C
errno_t _get_doserrno( 
   int * pValue 
);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
現在の値が格納される整数へのポインター、 **_doserrno**グローバル マクロ。

## <a name="return-value"></a>戻り値

場合 **_get_doserrno**成功すると、0 を返します。 エラー コードを返します、失敗した場合。 場合*pValue*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**EINVAL**です。

## <a name="remarks"></a>コメント

**_Doserrno** CRT の初期化中に 0 に設定されているグローバル マクロは、プロセスの前に実行が開始されます。 オペレーティング システム エラーを返すシステム レベルの関数呼び出しによって返されたオペレーティング システム エラー値に設定され、実行中に 0 にリセットされることはありません。 関数の場合、常にオフによって返されるエラー値をチェックするコードを記述するときに **_doserrno**を使用して[_set_doserrno](set-doserrno.md)関数呼び出しの前にします。 別の関数呼び出しが上書きされる可能性があるため **_doserrno**を使用して値をチェック **_get_doserrno**関数呼び出しの直後後です。

お勧め[_get_errno](get-errno.md)の代わりに **_get_doserrno**ポータブル エラー コード。

使用できる値 **_doserrno**で定義された\<<errno.h> >。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>、\<cstdlib> (C++)|\<errno.h>、\<cerrno> (C++)|

**_get_doserrno**は Microsoft 拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_set_doserrno](set-doserrno.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
