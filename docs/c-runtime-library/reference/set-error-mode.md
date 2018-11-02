---
title: _set_error_mode
ms.date: 11/04/2016
apiname:
- _set_error_mode
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
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 8c95ed45423b791a688f05ea30f48e188826a797
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502311"
---
# <a name="seterrormode"></a>_set_error_mode

変更 **_error_mode**を既定以外の場所が C ランタイムでのプログラムを終了する可能性がありますエラーのエラー メッセージの書き込み先を決定します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _set_error_mode(
   int mode_val
);
```

### <a name="parameters"></a>パラメーター

*mode_val*<br/>
エラー メッセージの書き込み先。

## <a name="return-value"></a>戻り値

エラーが発生した場合、以前の設定または-1 を返します。

## <a name="remarks"></a>Remarks

値を設定して、エラー出力シンクを制御 **_error_mode**します。 たとえば、出力を標準エラー出力またはを使用して、**メッセージ ボックス**API。

*Mode_val*パラメーターは、次の値のいずれかに設定することができます。

|パラメーター|説明|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|エラー シンクはによって決まります **__app_type**します。|
|**_OUT_TO_STDERR**|エラー シンクは、標準エラーです。|
|**_OUT_TO_MSGBOX**|エラー シンクは、メッセージ ボックスです。|
|**_REPORT_ERRMODE**|現在のレポート **_error_mode**値。|

リストされている以外の値が渡された場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 続けるには、実行が許可された場合 **_set_error_mode**設定**errno**に**EINVAL** -1 を返します。

と共に使用した場合、[アサート](assert-macro-assert-wassert.md)、 **_set_error_mode**  ダイアログ ボックスで失敗したステートメントを表示しを選択することができます、**無視**ボタンをクリックすることができます続行すると、プログラムを実行します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_set_error_mode**|\<stdlib.h>|

## <a name="example"></a>例

```C
// crt_set_error_mode.c
// compile with: /c
#include <stdlib.h>
#include <assert.h>

int main()
{
   _set_error_mode(_OUT_TO_STDERR);
   assert(2+2==5);
}
```

```Output
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>関連項目

[assert マクロ、_assert、_wassert](assert-macro-assert-wassert.md)<br/>
