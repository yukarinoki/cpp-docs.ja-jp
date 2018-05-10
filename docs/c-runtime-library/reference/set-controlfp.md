---
title: _set_controlfp | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_controlfp
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
- set_controlfp
- _set_controlfp
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2647e9719c2aa3fe303393fcc1da55de0385581
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="setcontrolfp"></a>_set_controlfp

浮動小数点制御ワードを設定します。

## <a name="syntax"></a>構文

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*newControl*<br/>
新しい制御ワードのビット値。

*マスク*<br/>
新しく設定する制御ワード ビットのマスク。

## <a name="return-value"></a>戻り値

なし。

## <a name="remarks"></a>コメント

**_Set_controlfp**関数がに似ていますが **_control87**を浮動小数点制御ワードにのみ設定が、 *newControl*です。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、無限大の各モードを変更できます。 マスクまたはを使用して浮動小数点の例外をマスク解除することができますも **_set_controlfp**です。 詳細については、「[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)」を参照してください。

コンパイルするときにこの関数は使用されなくなりました[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイムには、既定の浮動小数点精度のみがサポートされるためです。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|互換性|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|x86 プロセッサのみ|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87、_clearfp](clear87-clearfp.md)<br/>
[_status87、_statusfp、_statusfp2](status87-statusfp-statusfp2.md)<br/>
