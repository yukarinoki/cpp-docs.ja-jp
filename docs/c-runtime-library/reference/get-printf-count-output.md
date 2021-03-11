---
description: '詳細については、次を参照してください: _get_printf_count_output'
title: _get_printf_count_output
ms.date: 3/9/2021
api_name:
- _get_printf_count_output
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.openlocfilehash: f31c0321d2d7873db20e7d663918aebc002c768d
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "102622128"
---
# <a name="_get_printf_count_output"></a>_get_printf_count_output

[Printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)ファミリの各関数が **% n** 形式をサポートするかどうかを示します。

## <a name="syntax"></a>構文

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>戻り値

**% N** がサポートされている場合は0以外、 **% n** がサポートされていない場合は0です。

## <a name="remarks"></a>注釈

**% N** がサポートされていない場合 (既定)、いずれかの **printf** 関数の書式指定文字列で **% n** を検出すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 **% N** サポートが有効になっている場合 ( [_set_printf_count_output](set-printf-count-output.md)を参照)、 **% n** は [書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)の説明に従って動作します。

> [!IMPORTANT]
> Windows 10 バージョン 2004 (ビルド 19041) 以降では、 `printf` 関数ファミリは、丸め処理のために IEEE 754 の規則に従って、正確に表現可能な浮動小数点数を出力します。 以前のバージョンの Windows では、"5" で終わる厳密に表現可能な浮動小数点数は常に切り上げられます。 IEEE 754 では、最も近い偶数 ("銀行型丸め" とも呼ばれます) に丸める必要があることが示されています。 たとえば、との `printf("%1.0f", 1.5)` 両方 `printf("%1.0f", 2.5)` が2に丸められる必要があります。 以前は、1.5 は2に丸められ、2.5 は3に丸められていました。 この変更は、正確に表現できる数値にのみ影響します。 たとえば、2.35 (メモリで表される場合は2.35000000000000008 に近い) は、2.4 に切り上げられます。 これらの関数によって実行される丸め処理は、によって設定された浮動小数点丸めモードにも従い [`fesetround`](fegetround-fesetround2.md) ます。 以前は、常に丸め処理を選択していま `FE_TONEAREST` した。 この変更は、Visual Studio 2019 バージョン16.2 以降を使用してビルドされたプログラムにのみ影響します。 従来の浮動小数点丸め動作を使用するには、 [' legacy_stdio_float_rounding. .obj '](../link-options.md)にリンクします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

例については「[_set_printf_count_output](set-printf-count-output.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_set_printf_count_output](set-printf-count-output.md)<br/>
