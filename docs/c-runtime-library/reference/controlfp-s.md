---
title: _controlfp_s
ms.date: 04/05/2018
apiname:
- _controlfp_s
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
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 0624cbfb4870ca87efebac01a8de682b588a4ca3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506679"
---
# <a name="controlfps"></a>_controlfp_s

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

*newControl*<br/>
新しい制御ワードのビット値。

*マスク*<br/>
新しく設定する制御ワード ビットのマスク。

## <a name="return-value"></a>戻り値

成功した場合、または 0 **errno**エラー コードの値します。

## <a name="remarks"></a>Remarks

**_Controlfp_s**関数がプラットフォームに依存しないとより安全なバージョンの **_control87**に格納されているアドレスに浮動小数点制御ワードを取得する*currentControl*しを使用して設定*newControl*します。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードをプラットフォームに応じて変更できます。 使用することも **_controlfp_s**をマスクしたり、浮動小数点例外をマスク解除します。

場合の値は、*マスク*が 0、 **_controlfp_s**浮動小数点制御ワードを取得し、取得した値を*currentControl*します。

場合*マスク*が 0 以外の場合、制御ワードに新しい値が設定: ビットが設定のいずれか (つまり、1 に等しく) で*マスク*、対応するビット*新しい*コントロールを更新するために使用単語があります。 つまり、 *fpcntrl* = ((*fpcntrl* & ~*マスク*) &#124; (*newControl* & *マスク*))、 *fpcntrl*浮動小数点制御ワードです。 このシナリオで*currentControl*後の値に設定されている、変更の完了は、古い制御ワードのビット値ではありません。

> [!NOTE]
> 既定では、ランタイム ライブラリは、すべての浮動小数点例外をマスクします。

**_controlfp_s**とほとんど同じですが、 **_control87** intel (x86)、x64、および ARM プラットフォームに機能します。 使用することができる場合、x86、x64、または ARM プラットフォームを対象としている、 **_control87**または **_controlfp_s**します。

間の差 **_control87**と **_controlfp_s**が処理方法に非正規化値。 X64、ARM プラットフォームでは、intel (x86)、 **_control87**設定および DENORMAL OPERAND 例外マスクを解除できます。 **_controlfp_s** DENORMAL OPERAND 例外マスクを変更しません。 次の例に、この違いを示します。

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

マスク定数の有効な値 (*マスク*) とコントロールの新しい値 (*newControl*) の 16 進値の次の表を示します。 以下に示すポータブル定数を使用して (**_MCW_EM**、 **_EM_INVALID**など)、これらの関数に引数として、16 進数値を指定せずに明示的にします。

Intel (x86) から派生したプラットフォームでは、DENORMAL 入出力値がハードウェアでサポートされています。 x86 では DENORMAL 値を保持するように動作します。 ARM プラットフォームおよび SSE2 のプラットフォーム サポート x64 には、DENORMAL オペランドと結果をフラッシュするには、または強制的に 0 が有効にします。 **_Controlfp_s**、 **_controlfp**、および **_control87**関数は、この動作を変更するマスクを提供します。 このマスクの使用例を次に示します。

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM プラットフォームで、 **_controlfp_s**関数は FPSCR レジスタに適用されます。 X64 アーキテクチャでは、格納されている SSE2 制御ワードのみで、MXCSR レジスタが影響を受けます。 Intel (x86) プラットフォームで **_controlfp_s**存在する場合は x87 と SSE2 の両方の制御ワードに影響を与えます。 2 つの制御ワードが互いと矛盾する可能性が (以前の呼び出しにより[_ _control87_2](control87-controlfp-control87-2.md)など)、2 つの制御ワード間で不整合がある場合は **_controlfp_s**設定、 **EM_AMBIGUOUS**フラグ*currentControl*します。 これは、返された制御ワードが両方の浮動小数点制御ワードの状態を正確に表していない可能性があるという警告です。

ARM および x64 アーキテクチャでは、無限大モードまたは浮動小数点の精度の変更はサポートされていません。 精度の制御マスクが x64 で使用されるかどうか、関数、プラットフォーム、アサーションと」の説明に従って、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

マスクが正しく設定されていないと、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーターの例外を生成します。 かどうかは、引き続き実行が許可された、この関数を返します**EINVAL**設定と**errno**に**EINVAL**します。

使用する場合、この関数は無視されます[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイム (CLR) には、浮動小数点の既定の精度のみサポートしているため、コンパイルします。

### <a name="mask-constants-and-values"></a>マスク定数と値

**_MCW_EM**マスク、オフにすることは、例外は、ハードウェア例外を許可を設定します。 場合、例外を非表示に設定するとします。 場合、 **_EM_UNDERFLOW**または **_EM_OVERFLOW**発生すると、次の浮動小数点命令が実行されるまでハードウェア例外はスローされません。 ハードウェア例外を生成する後すぐに **_EM_UNDERFLOW**または **_EM_OVERFLOW**、FWAIT MASM 命令を呼び出します。

|マスク|16 進値|定数|16 進値|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (denormal 制御)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (割り込み例外マスク)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (無限制御)<br /><br /> (サポートされていません ARM または x64 プラットフォームです。)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (丸め制御)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (精度制御)<br /><br /> (サポートされていません ARM または x64 プラットフォームです。)|0x00030000|**_PC_24** (24 ビット)<br /><br /> **_PC_53** (53 ビット)<br /><br /> **_PC_64** (64 ビット)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
