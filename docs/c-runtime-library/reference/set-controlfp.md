---
title: _set_controlfp
ms.date: 04/05/2018
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
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 1187502f09849d7ca4d8e595c237cfa511d00c6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356687"
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

## <a name="remarks"></a>Remarks

**_Set_controlfp**機能に似ています **_control87**浮動小数点制御ワード設定だけを行いますが、 *newControl*します。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、無限大の各モードを変更できます。 マスクを使用して浮動小数点の例外をマスクの **_set_controlfp**します。 詳細については、「[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)」を参照してください。

コンパイルするときに、この関数は非推奨[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)のため、共通言語ランタイムは浮動小数点の既定の精度のみをサポートします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|互換性|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|x86 プロセッサのみ|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87、_clearfp](clear87-clearfp.md)<br/>
[_status87、_statusfp、_statusfp2](status87-statusfp-statusfp2.md)<br/>
