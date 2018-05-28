---
title: _RTC_SetErrorFunc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_SetErrorFunc
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
apitype: DLLExport
f1_keywords:
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
dev_langs:
- C++
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e146f699f9026260470b1c540c7567f074896a38
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc

実行時エラー チェック (RTC) を報告するためのハンドラーとして関数を指定します。 この関数は廃止されました。使用して **_RTC_SetErrorFuncW**代わりにします。

## <a name="syntax"></a>構文

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>パラメーター

*関数*<br/>
実行時エラー チェックを処理する関数のアドレス。

## <a name="return-value"></a>戻り値

以前に定義されたエラーの関数。 以前に定義された関数がない場合を返します**NULL**です。

## <a name="remarks"></a>コメント

この関数を使用しないでください。代わりに、 **_RTC_SetErrorFuncW**です。 これは下位互換性のためだけに残されています。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h>|

詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)<br/>
