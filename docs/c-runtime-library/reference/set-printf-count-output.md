---
title: _set_printf_count_output | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_printf_count_output
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
- set_printf_count_output
- _set_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96256f71a94f20f126f02b04511c57c831ad2a00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406642"
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output

有効にするにまたはのサポートを無効にする、 **%n**で書式設定[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-ファミリの関数。

## <a name="syntax"></a>構文

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>パラメーター

*有効にする*0 以外の値を有効にする **%n**サポートを無効にする場合は 0 **%n**をサポートします。

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

状態 **%n**この関数を呼び出す前にサポート: 0 以外の場合 **%n**サポートが有効になっていると、無効にされている場合は 0 です。

## <a name="remarks"></a>コメント

セキュリティ上の理由のためのサポート、 **%n**書式指定子が既定で無効になっている**printf**とそのすべてのバリエーション。 場合 **%n**で見つかりましたが、 **printf** 」の説明に従って、無効なパラメーター ハンドラーを呼び出すには、書式指定、既定の動作[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 呼び出す **_set_printf_count_output** 0 以外の引数を持つにより**printf**-ファミリの関数を解釈する **%n** 」の説明に従って[形式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_printf_count_output**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_set_printf_count_output.c
#include <stdio.h>

int main()
{
   int e;
   int i;
   e = _set_printf_count_output( 1 );
   printf( "%%n support was %sabled.\n",
        e ? "en" : "dis" );
   printf( "%%n support is now %sabled.\n",
        _get_printf_count_output() ? "en" : "dis" );
   printf( "12345%n6789\n", &i ); // %n format should set i to 5
   printf( "i = %d\n", i );
}
```

```Output
%n support was disabled.
%n support is now enabled.
123456789
i = 5
```

## <a name="see-also"></a>関連項目

[_get_printf_count_output](get-printf-count-output.md)<br/>
