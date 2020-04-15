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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 4b36cc9f5ed83b68cb15c39be91165ed7aa86d7b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348536"
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

*現在のコントロール*<br/>
現在の制御ワードのビット値。

*新しいコントロール*<br/>
新しい制御ワードのビット値。

*mask*<br/>
新しく設定する制御ワード ビットのマスク。

## <a name="return-value"></a>戻り値

成功した場合は 0、または**errno**値のエラー コード。

## <a name="remarks"></a>解説

**_controlfp_s**関数はプラットフォームに依存しない、より安全なバージョンの **_control87**で、浮動小数点コントロールワードを currentControl に格納されているアドレスに取得し *、newControl*を使用して設定します。 *currentControl* この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードをプラットフォームに応じて変更できます。 また **、_controlfp_s**を使用して、浮動小数点例外をマスクまたはマスク解除することもできます。

*mask*の値が 0 の場合 **、_controlfp_s**は浮動小数点コントロールワードを取得し、取得した値を*currentControl*に格納します。

*mask*が 0 以外の場合、制御ワードの新しい値が設定されます:*マスク*に設定されている任意のビット (つまり、1 に等しい) の場合 *、new*の対応するビットがコントロールワードの更新に使用されます。 つまり *、fpcntrl* = (fpcntrl & ~*マスク*) &#124; (*新しいコントロール* & *マスク*) *(fpcntrl*は浮動小数点制御語) です。*fpcntrl* このシナリオでは *、currentControl*は変更が完了した後、値に設定されます。これは、古い制御ワードビット値ではありません。

> [!NOTE]
> 既定では、ランタイム ライブラリは、すべての浮動小数点例外をマスクします。

**_controlfp_s**は、インテル (x86) 、x64、および ARM プラットフォームの **_control87**機能とほぼ同じです。 x86、x64、または ARM プラットフォームを対象としている場合は **、_control87**または **_controlfp_s**を使用できます。

**_control87**と **_controlfp_s**の違いは、非正規値の扱い方にあります。 インテル (x86)、x64、および ARM プラットフォームの場合 **、_control87**は DENORMAL オペランド例外マスクを設定およびクリアできます。 **_controlfp_s**は、非正規オペランド例外マスクを変更しません。 次の例に、この違いを示します。

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

マスク定数 (*マスク*) と新しいコントロール値 (*newControl*) の値を示す 16 進値の表を次に示します。 以下の移植可能な定数 (**_MCW_EM**、 **_EM_INVALID**など ) を、明示的に 16 進値を指定するのではなく、これらの関数の引数として使用します。

Intel (x86) から派生したプラットフォームでは、DENORMAL 入出力値がハードウェアでサポートされています。 x86 では DENORMAL 値を保持するように動作します。 ARM プラットフォームと SSE2 サポートを備えた x64 プラットフォームは、DENORMAL オペランドと結果をフラッシュするか、強制的にゼロにすることを可能にします。 **_controlfp_s**、 **_controlfp、** および **_control87**関数は、この動作を変更するためのマスクを提供します。 このマスクの使用例を次に示します。

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM プラットフォームでは **、_controlfp_s**機能は FPSCR レジスタに適用されます。 x64 アーキテクチャでは、MXCSR レジスタに格納されている SSE2 制御ワードのみが影響を受けます。 Intel (x86) プラットフォームでは **、_controlfp_s**は x87 と SSE2 の両方の制御ワードに影響を与えます (存在する場合)。 2 つの制御ワードが互いに矛盾している可能性があります (たとえば[、__control87_2](control87-controlfp-control87-2.md)への以前の呼び出しが原因で)。2 つの制御ワードの間に矛盾がある場合 **、_controlfp_s**は*currentControl*に**EM_AMBIGUOUS**フラグを設定します。 これは、返された制御ワードが両方の浮動小数点制御ワードの状態を正確に表していない可能性があるという警告です。

ARM および x64 アーキテクチャでは、無限大モードまたは浮動小数点精度の変更はサポートされていません。 x64 プラットフォームで精度コントロール マスクを使用すると、関数はアサーションを発生させ、無効なパラメータ ハンドラが呼び出されます[。](../../c-runtime-library/parameter-validation.md)

マスクが正しく設定されていないと、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーターの例外を生成します。 実行を続行できる場合、この関数は**EINVAL**を返し **、errno**を**EINVAL**に設定します。

共通言語ランタイム (CLR) では既定の浮動小数点の精度しかサポートしていないため、コンパイルに[/clr (共通言語ランタイム コンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)を使用する場合、この関数は無視されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="mask-constants-and-values"></a>定数と値をマスクする

**_MCW_EM**マスクの場合、それをクリアすると、例外が設定され、ハードウェア例外が許可されます。この値を設定すると、例外は非表示になります。 **_EM_UNDERFLOW**または **_EM_OVERFLOW**が発生した場合、次の浮動小数点命令が実行されるまで、ハードウェア例外はスローされません。 **_EM_UNDERFLOW**または_EM_OVERFLOW直後にハードウェア例外を生成するには **、FWAIT**MASM 命令を呼び出します。

|Mask|16 進値|定数|16 進値|
|----------|---------------|--------------|---------------|
|**_MCW_DN(** 非正規制御)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (割り込み例外マスク)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (インフィニティコントロール)<br /><br /> (ARM または x64 プラットフォームではサポートされていません。|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (丸め制御)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (精密制御)<br /><br /> (ARM または x64 プラットフォームではサポートされていません。|0x00030000|**_PC_24** (24 ビット)<br /><br /> **_PC_53** (53 ビット)<br /><br /> **_PC_64** (64 ビット)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

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
