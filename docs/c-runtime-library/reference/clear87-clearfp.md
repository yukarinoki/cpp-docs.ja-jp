---
title: _clear87、_clearfp
ms.date: 04/05/2018
apiname:
- _clearfp
- _clear87
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
- clearfp
- _clearfp
- _clear87
- clear87
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
ms.openlocfilehash: 4148f85d82a4210033686455c73046081832e3c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477260"
---
# <a name="clear87-clearfp"></a>_clear87、_clearfp

浮動小数点ステータス ワードを取得し、クリアします。

## <a name="syntax"></a>構文

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>戻り値

返される値のビットは、呼び出しの前に、浮動小数点のステータスを示します。 **_clear87**または **_clearfp**します。 によって返されるビットの定義の **_clear87**Float.h を参照してください。 多くの数値演算ライブラリ関数は、8087/80287 ステータス ワードを変更しますが、その結果は予測できません。 値を返す **_clear87**と **_status87**より少ない浮動小数点演算が浮動小数点ステータス ワードの既知の状態の間で実行される、信頼性が高くなります。

## <a name="remarks"></a>Remarks

**_Clear87**関数の浮動小数点ステータス ワードの例外フラグのクリア、ビジー ビットを 0 に設定およびステータス ワードを返します。 浮動小数点ステータス ワードは、8087/80287 ステータス ワードと、8087/80287 例外ハンドラーによって検出された浮動小数点スタック オーバーフローやアンダーフローなど、ほかの条件との組み合わせです。

**_clearfp**のプラットフォームに依存しない、移植可能なバージョンは、 **_clear87**ルーチン。 これは **_clear87** Intel (x86) プラットフォームでは、x64 および ARM プラットフォームによってもサポートされています。 浮動小数点コードが x64 および ARM に移植可能であることを確認するには使用 **_clearfp**します。 X86 を対象としているだけの場合、プラットフォームを使用できます **_clear87**または **_clearfp**。

コンパイルするときに、これらの関数は非推奨[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)のため、共通言語ランタイムは浮動小数点の既定の精度のみをサポートします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_clear87**|\<float.h>|
|**_clearfp**|\<float.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_clear87.c
// compile with: /Od

// This program creates various floating-point
// problems, then uses _clear87 to report on these problems.
// Compile this program with Optimizations disabled (/Od).
// Otherwise the optimizer will remove the code associated with
// the unused floating-point values.
//

#include <stdio.h>
#include <float.h>

int main( void )
{
   double a = 1e-40, b;
   float x, y;

   printf( "Status: %.4x - clear\n", _clear87()  );

   // Store into y is inexact and underflows:
   y = a;
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );

   // y is denormal:
   b = y;
   printf( "Status: %.4x - denormal\n", _clear87() );
}
```

```Output
Status: 0000 - clear
Status: 0003 - inexact, underflow
Status: 80000 - denormal
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)<br/>
[_status87、_statusfp、_statusfp2](status87-statusfp-statusfp2.md)<br/>
