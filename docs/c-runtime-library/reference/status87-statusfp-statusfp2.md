---
title: _status87、_statusfp、_statusfp2
ms.date: 04/05/2018
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
ms.openlocfilehash: 271c28dd4e267e5b3b702858cc398689e3e35d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354432"
---
# <a name="status87-statusfp-statusfp2"></a>_status87、_statusfp、_statusfp2

浮動小数点ステータス ワードを取得します。

## <a name="syntax"></a>構文

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>パラメーター

*px86*<br/>
このアドレスには、x87 浮動小数点ユニットのステータス ワードが格納されます。

*pSSE2*<br/>
このアドレスには、SSE2 浮動小数点ユニットのステータス ワードが格納されます。

## <a name="return-value"></a>戻り値

**_Status87**と **_statusfp**、返される値のビットは浮動小数点のステータスを示します。 浮動小数点数を参照してください。H によって返されるビットの定義のファイルをインクルードする **_statusfp**します。 多くの数値演算ライブラリ関数は、予測できない結果を使用して浮動小数点ステータス ワードを変更します。 順序を変更、結合、および浮動小数点演算の呼び出しの周りを排除できる最適化 **_status87**、 **_statusfp**、および関連する関数。 浮動小数点演算の順序を変更する最適化を防ぐには、[/Od (無効 (デバッグ))](../../build/reference/od-disable-debug.md) コンパイラ オプションまたは [fenv_access](../../preprocessor/fenv-access.md) プラグマ ディレクティブを使用します。 値を返す **_clearfp**と **_statusfp**、および戻り値のパラメーターも **_statusfp2**より少ない浮動小数点演算が実行された場合、信頼性が高く、浮動小数点ステータス ワードの既知の状態間。

## <a name="remarks"></a>Remarks

**_Statusfp**関数は浮動小数点ステータス ワードを取得します。 ステータス ワードとは、浮動小数点例外によって検出された浮動小数点プロセッサのステータスやその他の条件 (浮動小数点スタック オーバーフローおよびアンダーフローなど) の組み合わせです。 マスクされていない例外は、ステータス ワードのコンテンツが返される前にチェックされます。 これは、呼び出し元に保留中の例外を通知することを意味します。 X86 プラットフォームでは、 **_statusfp**は x87 と SSE2 浮動小数点ステータスの組み合わせを返します。 x64 プラットフォームでは、返される状態は、SSE の MXCSR の状態に基づいています。 ARM プラットフォームで **_statusfp** FPSCR レジスタからステータスを返します。

**_statusfp**のプラットフォームに依存しない、移植可能なバージョンは、 **_status87**します。 これは **_status87** Intel (x86) プラットフォームでは、x64 および ARM プラットフォームによってもサポートされています。 浮動小数点コードがすべてのアーキテクチャに移植可能であることを確認するには使用 **_statusfp**します。 X86 を対象としているだけの場合、プラットフォームを使用できます **_status87**または **_statusfp**。

お勧め **_statusfp2**を x87 および SSE2 の浮動小数点プロセッサの両方を持つチップ (Pentium IV) など。 **_Statusfp2**アドレスは、x87 または SSE2 浮動小数点プロセッサの両方の浮動小数点ステータス ワードを使用して設定します。 X87 と SSE2 浮動小数点プロセッサをサポートするチップ、EM_AMBIGUOUS が 1 の場合に設定されて **_statusfp**または **_controlfp**使用されていて、x87 または SSE2 を参照しているため、操作があいまいですが浮動小数点ステータス ワード。 **_Statusfp2**関数が x86 上でのみサポートされているプラットフォーム。

これらの関数は適していない[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイム (CLR) には、浮動小数点の既定の精度だけがサポートされます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_status87**、 **_statusfp**、 **_statusfp2**|\<float.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_statusfp.c
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c
// This program creates various floating-point errors and
// then uses _statusfp to display messages that indicate these problems.

#include <stdio.h>
#include <float.h>
#pragma fenv_access(on)

double test( void )
{
   double a = 1e-40;
   float b;
   double c;

   printf("Status = 0x%.8x - clear\n", _statusfp());

   // Assignment into b is inexact & underflows:
   b = (float)(a + 1e-40);
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());

   // c is denormal:
   c = b / 2.0;
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",
            _statusfp());

   // Clear floating point status:
   _clearfp();
   return c;
}

int main(void)
{
   return (int)test();
}
```

```Output
Status = 0x00000000 - clear
Status = 0x00000003 - inexact, underflow
Status = 0x00080003 - inexact, underflow, denormal
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87、_clearfp](clear87-clearfp.md)<br/>
[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)<br/>
