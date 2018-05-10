---
title: _set_error_mode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 130e9fee13401c8b598a5d6eef7d1fab3ed80ae9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="seterrormode"></a>_set_error_mode

変更 **_error_mode**を既定以外の場所が C ランタイムが、プログラムを終了する可能性があります、エラーのエラー メッセージを書き込む場所を決定します。

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

## <a name="remarks"></a>コメント

値を設定して、エラー出力シンクを制御 **_error_mode**です。 たとえばに標準エラー出力を転送したり、使用、 **MessageBox** API です。

*Mode_val*パラメーターは、次の値のいずれかに設定することができます。

|パラメーター|説明|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|エラー シンクはによって決まります **__app_type**です。|
|**_OUT_TO_STDERR**|エラー シンクは、標準エラーです。|
|**_OUT_TO_MSGBOX**|エラー シンクは、メッセージ ボックスです。|
|**_REPORT_ERRMODE**|現在のレポート **_error_mode**値。|

リストされている以外の値が渡された場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 続けるには、実行が許可された場合 **_set_error_mode**設定**errno**に**EINVAL**し、-1 を返します。

使用した場合、[アサート](assert-macro-assert-wassert.md)、 **_set_error_mode**  ダイアログ ボックスで、障害が発生したステートメントを表示し、選択した場合のオプションを選択できます、**無視**ボタンをクリックすることができますプログラムを実行し続けます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
