---
description: '詳細については、次を参照してください: _set_controlfp'
title: _set_controlfp
ms.date: 04/05/2018
api_name:
- _set_controlfp
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_controlfp
- _set_controlfp
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 44316cb4114d06ced1b3d67a261bc8d3ceb1aee6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288868"
---
# <a name="_set_controlfp"></a>_set_controlfp

浮動小数点制御ワードを設定します。

## <a name="syntax"></a>構文

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*基準*<br/>
新しい制御ワードのビット値。

*隠す*<br/>
新しく設定する制御ワード ビットのマスク。

## <a name="return-value"></a>戻り値

[なし] :

## <a name="remarks"></a>解説

**_Set_controlfp** 関数は **_control87** に似ていますが、浮動小数点制御ワードのみが *newcontrol* に設定されます。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、無限大の各モードを変更できます。 **_Set_controlfp** を使用して、浮動小数点例外のマスクやマスク解除を行うこともできます。 詳細については、「[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)」を参照してください。

共通言語ランタイムは浮動小数点の既定の精度のみをサポートするため、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) を使用してコンパイルする場合、この関数は非推奨とされます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|互換性|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|x86 プロセッサのみ|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87、_clearfp](clear87-clearfp.md)<br/>
[_status87、_statusfp、_statusfp2](status87-statusfp-statusfp2.md)<br/>
