---
title: _controlfp_s
ms.date: 4/2/2020
api_name:
- _controlfp_s
- _o__controlfp_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 0e734a0286ac21ed0883cc10b0cd4ee5857ba448
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917266"
---
# <a name="_controlfp_s"></a>_controlfp_s

浮動小数点制御ワードの取得および設定を行います。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md) です。

## <a name="syntax"></a>構文

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*currentControl*<br/>
現在の制御ワードのビット値。

*基準*<br/>
新しい制御ワードのビット値。

*mask*<br/>
新しく設定する制御ワード ビットのマスク。

## <a name="return-value"></a>戻り値

成功した場合は0、または**errno**値エラーコード。

## <a name="remarks"></a>解説

**_Controlfp_s**関数は、プラットフォームに依存しない、より安全なバージョンの **_control87**であり、浮動小数点制御ワードを*currentcontrol*に格納されているアドレスに取得し、 *newcontrol*を使用して設定します。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードをプラットフォームに応じて変更できます。 **_Controlfp_s**を使用して、浮動小数点例外のマスクやマスク解除を行うこともできます。

*Mask*の値が0の場合、 **_controlfp_s**は浮動小数点制御ワードを取得し、取得した値を*currentcontrol*に格納します。

*Mask*が0以外の場合、制御ワードの新しい値が設定されます。*マスク*で設定されている (つまり1に等しい) 任意のビットに対して、 *new*の対応するビットが制御ワードの更新に使用されます。 言い換えると、 *fpcntrl* = ((*fpcntrl* & ~*mask*) &#124; (*newcontrol* & *mask*)) では、 *fpcntrl*は浮動小数点制御ワードです。 このシナリオでは、変更が完了した後に*Currentcontrol*が値に設定されます。これは、古い制御ワードのビット値ではありません。

> [!NOTE]
> 既定では、ランタイム ライブラリは、すべての浮動小数点例外をマスクします。

**_controlfp_s**は、Intel (x86)、x64、および ARM プラットフォームの **_control87**関数とほぼ同じです。 X86、x64、または ARM プラットフォームを対象としている場合は、 **_control87**または **_controlfp_s**を使用できます。

**_Control87**と **_controlfp_s**の違いは、denormal 値の扱い方です。 Intel (x86)、x64、および ARM プラットフォームの場合、 **_control87**は DENORMAL オペランドの例外マスクを設定およびクリアできます。 **_controlfp_s**では、DENORMAL オペランドの例外マスクは変更されません。 次の例に、この違いを示します。

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

マスク定数 (*mask*) と新しいコントロール値 (*newcontrol*) に使用できる値は、次の16進値の表に示されています。 16進数値を明示的に指定するのではなく、以下に示すような移植性の高い定数 (**_MCW_EM**、 **_EM_INVALID**など) をこれらの関数の引数として使用します。

Intel (x86) から派生したプラットフォームでは、DENORMAL 入出力値がハードウェアでサポートされています。 x86 では DENORMAL 値を保持するように動作します。 ARM プラットフォームおよび SSE2 をサポートする x64 プラットフォームでは、DENORMAL のオペランドと結果をフラッシュするか、強制的にゼロにすることができます。 **_Controlfp_s**、 **_controlfp**、および **_control87**の各関数は、この動作を変更するマスクを提供します。 このマスクの使用例を次に示します。

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM プラットフォームでは、 **_controlfp_s**関数は、fpscr レジスタに適用されます。 X64 アーキテクチャでは、MXCSR レジスタに格納されている SSE2 制御ワードのみが影響を受けます。 Intel (x86) プラットフォームでは、 **_controlfp_s**は X87 と SSE2 の両方の制御ワードに影響します (存在する場合)。 2つの制御ワードが相互に一貫性を持たない可能性があります (たとえば、 [__control87_2](control87-controlfp-control87-2.md)を以前に呼び出したためです)。2つの制御ワードの間に矛盾がある場合、 **_controlfp_s**は*currentcontrol*で**EM_AMBIGUOUS**フラグを設定します。 これは、返された制御ワードが両方の浮動小数点制御ワードの状態を正確に表していない可能性があるという警告です。

ARM および x64 アーキテクチャでは、無限大モードまたは浮動小数点の精度の変更はサポートされていません。 有効桁数の制御マスクが x64 プラットフォームで使用されている場合、関数はアサーションを発生させ、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。

マスクが正しく設定されていないと、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーターの例外を生成します。 実行の継続が許可された場合、この関数は**einval**を返し、 **errno**を**einval**に設定します。

共通言語ランタイム (CLR) は浮動小数点の既定の精度のみをサポートするため、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)を使用してコンパイルすると、この関数は無視されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="mask-constants-and-values"></a>定数と値をマスクする

**_MCW_EM**マスクの場合、これをオフにすると、ハードウェア例外を許可する例外が設定されます。設定すると、例外が非表示になります。 **_EM_UNDERFLOW**または **_EM_OVERFLOW**が発生した場合、次の浮動小数点命令が実行されるまで、ハードウェア例外はスローされません。 **_EM_UNDERFLOW**または **_EM_OVERFLOW**の直後にハードウェア例外を生成するには、fwait MASM 命令を呼び出します。

|Mask|16 進値|定数|16 進値|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Denormal コントロール)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (割り込み例外マスク)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (無限大制御)<br /><br /> (ARM または x64 プラットフォームではサポートされていません)。|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (丸め制御)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (精度制御)<br /><br /> (ARM または x64 プラットフォームではサポートされていません)。|0x00030000|**_PC_24** (24 ビット)<br /><br /> **_PC_53** (53 ビット)<br /><br /> **_PC_64** (64 ビット)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_contrlfp_s.c
// processor: x86
// This program uses _controlfp_s to output the FP control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word;
    int err;

    // Show original FP control word and do calculation.
    err = _controlfp_s(&control_word, 0, 0);
    if ( err ) /* handle error here */;

    printf( "Original: 0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "24-bit:   0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "Default:  0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x9001f
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0xa001f
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x9001f
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87、_clearfp](clear87-clearfp.md)<br/>
[_status87、_statusfp、_statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)<br/>
