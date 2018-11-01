---
title: _RTC_SetErrorFunc
ms.date: 11/04/2016
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
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
ms.openlocfilehash: 6b292d685eea8eccb9e9b2a3c3e6cd903d501005
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514739"
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc

実行時エラー チェック (RTC) を報告するためのハンドラーとして関数を指定します。 この関数が非推奨とされます。使用して、 **_RTC_SetErrorFuncW**代わりにします。

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

以前に定義されたエラーの関数。 以前に定義された関数がない場合は、返す**NULL**します。

## <a name="remarks"></a>Remarks

この関数を使用しないでください。代わりに、 **_RTC_SetErrorFuncW**します。 これは下位互換性のためだけに残されています。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h>|

詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)<br/>
