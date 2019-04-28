---
title: _fpieee_flt
ms.date: 04/05/2018
apiname:
- _fpieee_flt
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
- fpieee_flt
- _fpieee_flt
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
ms.openlocfilehash: 9a49ec403b1cb95407b0a366accf1d9374d9cb22
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333249"
---
# <a name="fpieeeflt"></a>_fpieee_flt

IEEE 浮動小数点例外用のユーザー定義トラップ ハンドラーを呼び出します。

## <a name="syntax"></a>構文

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>パラメーター

*excCode*<br/>
例外コード。

*excInfo*<br/>
Windows NT 例外情報構造体へのポインター。

*ハンドラー*<br/>
ユーザーの IEEE トラップ ハンドラー ルーチンへのポインター。

## <a name="return-value"></a>戻り値

戻り値 **_fpieee_flt**によって返される値は、*ハンドラー*します。 そのため、構造化例外処理 (SEH) 機構の except 句で IEEE フィルター ルーチンが使用される場合があります。

## <a name="remarks"></a>Remarks

**_Fpieee_flt**関数は、IEEE 浮動小数点例外用のユーザー定義トラップ ハンドラーを呼び出し、すべての関連情報が提供されます。 このルーチンは SEH 機構の例外フィルターとして機能し、必要に応じて独自の IEEE 例外ハンドラーが呼び出されます。

**_FPIEEE_RECORD** Fpieee.h で定義されている構造には、IEEE 浮動小数点例外に関する情報が含まれています。 この構造体は、ユーザー定義トラップ ハンドラーに渡される **_fpieee_flt**します。

|_FPIEEE_RECORD フィールド|説明|
|----------------------------|-----------------|
|**RoundingMode**<br/>**精度**|これら**符号なし** **int**例外が発生した時点での浮動小数点環境に関する情報を格納します。|
|**操作**|これは、**符号なし** **int**フィールド、トラップを原因となった操作の種類を示します。 型が比較の場合 (**_FpCodeCompare**)、特殊なのいずれかを指定できます **_FPIEEE_COMPARE_RESULT**値 (fpieee.h 内で定義されている) で、 **Result.Value**フィールド。 変換の種類 (**_FpCodeConvert**) 浮動小数点の変換操作中に、トラップが発生したことを示します。 見ることができます、 **Operand1**と**結果**型を変換しようとしているの種類を確認します。|
|**Operand1**<br/>**オペランド 2**<br/>**結果**|これら **_FPIEEE_VALUE**構造型と提案された結果とオペランドの値を指定します。 各構造体には、これらのフィールドが含まれています。<br /><br /> **OperandValid** - 応答の値が有効かどうかを示すフラグ。<br />**形式**-対応する値のデータ型。 対応する値が有効でなくても、形式の種類が返されることがあります。<br />**値**-結果またはオペランドのデータ値。|
|**原因**<br/>**Enable**<br/>**状態**|**_Fpieee_exception_flags に**浮動小数点例外の種類ごとに 1 つのビット フィールドが含まれています。 これらのフィールドと、[_controlfp](control87-controlfp-control87-2.md) に指定される例外をマスクするために使用される引数との間には対応関係があります。 各ビットの正確な意味はコンテキストに依存します。<br /><br /> **原因**-特定の例外が発生したことを示します各ビットを設定します。<br />**有効にする**-ビットに設定されている各は、特定の例外が現在はマスクされていないことを示します。<br />**ステータス**-ビットに設定されている各は、特定の例外が現在保留中であることを示します。 これによってマスクされたために発生していない例外が含まれます **_controlfp**します。|

無効になっている保留中の例外は、有効にされたときに発生します。 これにより、未定義の動作を使用する場合 **_fpieee_flt**を例外フィルターとして。 浮動小数点例外を有効にする前に、必ず [_clearfp](clear87-clearfp.md) を呼び出してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fpieee.c
// This program demonstrates the implementation of
// a user-defined floating-point exception handler using the
// _fpieee_flt function.

#include <fpieee.h>
#include <excpt.h>
#include <float.h>
#include <stddef.h>

int fpieee_handler( _FPIEEE_RECORD * );

int fpieee_handler( _FPIEEE_RECORD *pieee )
{
   // user-defined ieee trap handler routine:
   // there is one handler for all
   // IEEE exceptions

   // Assume the user wants all invalid
   // operations to return 0.

   if ((pieee->Cause.InvalidOperation) &&
       (pieee->Result.Format == _FpFormatFp32))
   {
        pieee->Result.Value.Fp32Value = 0.0F;

        return EXCEPTION_CONTINUE_EXECUTION;
   }
   else
      return EXCEPTION_EXECUTE_HANDLER;
}

#define _EXC_MASK    \
    _EM_UNDERFLOW  + \
    _EM_OVERFLOW   + \
    _EM_ZERODIVIDE + \
    _EM_INEXACT

int main( void )
{
   // ...

   __try {
      // unmask invalid operation exception
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);

      // code that may generate
      // fp exceptions goes here
   }
   __except ( _fpieee_flt( GetExceptionCode(),
                GetExceptionInformation(),
                fpieee_handler ) ){

      // code that gets control

      // if fpieee_handler returns
      // EXCEPTION_EXECUTE_HANDLER goes here

   }

   // ...
}
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_control87、_controlfp、\__control87_2](control87-controlfp-control87-2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
