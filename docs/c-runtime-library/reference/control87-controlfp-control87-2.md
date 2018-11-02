---
title: _control87、_controlfp、__control87_2
ms.date: 04/05/2018
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
ms.openlocfilehash: e2ebfdc80a451ebf02563f78a62dd08618f92bcd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505873"
---
# <a name="control87-controlfp-control872"></a>_control87、_controlfp、__control87_2

浮動小数点制御ワードの取得および設定を行います。 より安全なバージョン **_controlfp**が利用できるを参照してください。 [_controlfp_s](controlfp-s.md)します。

## <a name="syntax"></a>構文

```C
unsigned int _control87(
   unsigned int new,
   unsigned int mask
);
unsigned int _controlfp(
   unsigned int new,
   unsigned int mask
);
int __control87_2(
   unsigned int new,
   unsigned int mask,
   unsigned int* x86_cw,
   unsigned int* sse2_cw
);
```

### <a name="parameters"></a>パラメーター

*new*<br/>
新しい制御ワードのビット値。

*マスク*<br/>
新しく設定する制御ワード ビットのマスク。

*x86_cw*<br/>
x87 浮動小数点ユニットの制御ワードが格納されます。 0 を渡します (**NULL**) SSE2 制御ワードのみを設定します。

*sse2_cw*<br/>
SSE 浮動小数点ユニットの制御ワード。 0 を渡します (**NULL**) x87 のみを設定する制御ワード。

## <a name="return-value"></a>戻り値

**_Control87**と **_controlfp**、浮動小数点のコントロールの状態を示す値のビットが返されます。 によって返されるビットの定義の **_control87**FLOAT を参照してください。H.

**_ _Control87_2**、戻り値は 1 で、成功を示します。

## <a name="remarks"></a>Remarks

**_Control87**関数を取得し、浮動小数点制御ワードを設定します。 浮動小数点制御ワードを使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードをプラットフォームに応じて変更できます。 使用することも **_control87**をマスクしたり、浮動小数点例外をマスク解除します。 場合の値は、*マスク*が 0、 **_control87**浮動小数点制御ワードを取得します。 場合*マスク*が 0 以外の場合、制御ワードに新しい値が設定: の上にあるいずれかのビット (つまり、1 に等しく) で*マスク*、対応するビット*新しい*コントロールを更新するために使用単語があります。 つまり、 **fpcntrl** = ((**fpcntrl** & ~*マスク*) &#124; (*新しい* & *マスク*))場所**fpcntrl**浮動小数点制御ワードです。

> [!NOTE]
> 既定では、ランタイム ライブラリは、すべての浮動小数点例外をマスクします。

**_controlfp**のプラットフォームに依存しない、移植可能なバージョンは、 **_control87**します。 ほぼ同じですが、 **_control87** x86、x64、および ARM プラットフォームで機能します。 X86、x64、または ARM プラットフォームをターゲットにする場合を使用して、 **_control87**または **_controlfp**します。

間の差 **_control87**と **_controlfp** DENORMAL 値の処理方法にします。 X86、x64、および ARM プラットフォームでは、 **_control87**設定および DENORMAL OPERAND 例外マスクを解除できます。 **_controlfp** DENORMAL OPERAND 例外マスクを変更しません。 次の例に、この違いを示します。

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

マスク定数の有効な値 (*マスク*) とコントロールの新しい値 (*新しい*) の 16 進値の次の表を示します。 以下に示すポータブル定数を使用して (**_MCW_EM**、 **_EM_INVALID**など)、これらの関数に引数として、16 進数値を指定せずに明示的にします。

Intel x86 から派生したプラットフォームでは、DENORMAL 入力をサポートして、出力ハードウェアでの値。 x86 では DENORMAL 値を保持するように動作します。 ARM プラットフォームおよび SSE2 のプラットフォーム サポート x64 には、DENORMAL オペランドと結果をフラッシュするには、または強制的に 0 が有効にします。 **_Controlfp**と **_control87**関数は、この動作を変更するマスクを提供します。 このマスクの使用例を次に示します。

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM プラットフォームで、 **_control87**と **_controlfp**関数は FPSCR レジスタに適用されます。 X64 アーキテクチャでは、格納されている SSE2 制御ワードのみで、MXCSR レジスタが影響を受けます。 X86 プラットフォームでは、 **_control87**と **_controlfp**存在する場合は x87 と SSE2 の両方の制御ワードに影響します。 関数は、 **_ _control87_2**は x87 と SSE2 の浮動小数点ユニットを単独でまたは組み合わせて制御の両方を使用します。 両方のユニットに影響する場合に 2 つの整数のアドレスを渡す**x86_cw**と**sse2_cw**します。 1 つのユニットに影響する場合は、そのパラメーターのアドレスを渡しますが、0 を渡します (**NULL**)、その他のです。 いずれかのパラメーターに対して 0 が渡されると、関数はその浮動小数点ユニットには影響しません。 この機能は、コードの一部では x87 浮動小数点ユニットを使用し、別の部分では SSE2 浮動小数点ユニットを使用する場合に役立ちます。 使用する場合 **_ _control87_2**プログラムの 1 つの部分での浮動小数点制御ワード、別の値を設定しを使用して **_control87**または **_controlfp**をさらに制御ワードを操作 **_control87**と **_controlfp**を両方の浮動小数点ユニットの状態を表す単一の制御ワードを返すことがない可能性があります。 このような場合は、これらの関数の設定、 **EM_AMBIGUOUS**を 2 つの制御ワード間で不整合があることを示す整数の戻り値のフラグ。 これは、返された制御ワードが両方の浮動小数点制御ワードの状態を正確に表していない可能性があるという警告です。

ARM および x64 アーキテクチャでは、無限大モードまたは浮動小数点の精度の変更はサポートされていません。 精度の制御マスクが x64 で使用されるかどうか、関数、プラットフォーム、アサーションと」の説明に従って、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

> [!NOTE]
> **_ _control87_2** ARM または x64 ではサポートされていませんアーキテクチャ。 使用する場合 **_ _control87_2**プログラムをコンパイル、ARM または x64 のアーキテクチャでは、コンパイラ エラーが発生します。

使用する場合、これらの関数は無視されます[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイム (CLR) には、浮動小数点の既定の精度のみサポートしているため、コンパイルします。

**16 進数の値**

**_MCW_EM**マスク、マスク オフにすると、例外は、ハードウェア例外を許可の設定は、例外を非表示にマスクを設定します。 場合、 **_EM_UNDERFLOW**または **_EM_OVERFLOW**発生すると、次の浮動小数点命令が実行されるまでハードウェア例外はスローされません。 ハードウェア例外を生成する後すぐに **_EM_UNDERFLOW**または **_EM_OVERFLOW**を呼び出し、 **FWAIT** MASM 命令。

|マスク|16 進値|定数|16 進値|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (denormal 制御)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (割り込み例外マスク)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (無限制御)<br /><br /> (ARM または x64 ではサポートされていません] プラットフォームです)。|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (丸め制御)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (精度制御)<br /><br /> (サポートされていません ARM または x64 プラットフォームです。)|0x00030000|**_PC_24** (24 ビット)<br /><br /> **_PC_53** (53 ビット)<br /><br /> **_PC_64** (64 ビット)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_control87**、 **_controlfp**、 **_control87_2**|\<float.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_cntrl87.c
// processor: x86
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87;

    // Show original x87 control word and do calculation.
    control_word_x87 = __control87_2(0, 0,
                                     &control_word_x87, 0);
    printf( "Original: 0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    control_word_x87 = __control87_2(_PC_24, MCW_PC,
                                     &control_word_x87, 0);
    printf( "24-bit:   0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,
                                     &control_word_x87, 0 );
    printf( "Default:  0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0001
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0x0001
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x0001
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87、_clearfp](clear87-clearfp.md)<br/>
[_status87、_statusfp、_statusfp2](status87-statusfp-statusfp2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
