---
title: _get_output_format |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
dev_langs:
- C++
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 410677f252dca6ff3d7fba4969b27cf3a18b12ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="getoutputformat"></a>_get_output_format
出力形式フラグの現在の値を取得します。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _get_output_format();  
```  
  
## <a name="return-value"></a>戻り値  
 出力形式フラグの現在の値。  
  
## <a name="remarks"></a>コメント  
 出力形式フラグは、書式付き I/O の機能を制御します。 現在、このフラグに指定できるのは 0 と `_TWO_DIGIT_EXPONENT`という 2 つの値です。 `_TWO_DIGIT_EXPONENT` に設定すると、指数部の大きさによって 3 桁目が必要になる場合を除いて、浮動小数点数の指数部は 2 桁のみで出力されます。 このフラグを 0 に設定すると、浮動小数点数の指数部は 3 桁で出力され、必要な場合は 0 を埋め込んで 3 桁にされます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_get_output_format`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
[書式指定構文: printf 関数と wprintf 関数](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)  
 [printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_set_output_format](../c-runtime-library/set-output-format.md)  
