---
title: _matherr
ms.date: 04/05/2018
apiname:
- _matherr
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
apitype: DLLExport
f1_keywords:
- _matherr
- matherr
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
ms.openlocfilehash: b830dc940fa2abb131f70130033d27b057412137
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156916"
---
# <a name="matherr"></a>_matherr

数値演算エラーを処理します。

## <a name="syntax"></a>構文

```C
int _matherr( struct _exception * except );
```

### <a name="parameters"></a>パラメーター

*except*<br/>
エラー情報を保持する構造体へのポインター。

## <a name="return-value"></a>戻り値

**_matherr** 、エラーまたは成功を示すゼロ以外の値を示す 0 を返します。 場合 **_matherr**返します 0、エラー メッセージを表示できると**errno**該当するエラー値に設定されます。 場合 **_matherr**返します 0 以外の値、エラー メッセージが表示されますおよび**errno**は変更されません。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

**_Matherr**関数は、数値演算ライブラリの浮動小数点関数によって生成されたエラーを処理します。 これらの関数を呼び出す **_matherr**エラーが検出されたとき。

特別なエラー処理のための別の定義を行うことができます **_matherr**します。 C ランタイム ライブラリ (CRT) の動的にリンクされているバージョンを使用する場合は、既定値を置き換えることができます **_matherr**クライアントのユーザー定義のバージョンで実行可能ファイルでルーチン。 既定値を置き換えることはできませんただし、 **_matherr** CRT DLL の DLL クライアント内に日常的な。

数値演算ルーチンでエラーが発生したときに **_matherr**へのポインターを使用して呼び出した、 **_exception**構造体の型 (で定義されている\<math.h >) を引数として。 **_exception** 構造体には次の要素が含まれます。

```C
struct _exception
{
    int    type;   // exception type - see below
    char*  name;   // name of function where error occurred
    double arg1;   // first argument to function
    double arg2;   // second argument (if any) to function
    double retval; // value to be returned by function
};
```

**型**メンバーは、数値演算エラーの種類を指定します。 定義されている、次の値のいずれかの\<math.h >:

|マクロ|説明|
|-|-|
| **_DOMAIN** | 引数のドメイン エラー |
| **_SING** | 引数の特異点 |
| **_OVERFLOW** | オーバーフロー範囲エラー |
| **_PLOSS** | 有効桁の部分的な損失 |
| **_TLOSS** | 基準値の合計が失われる |
| **_UNDERFLOW** | 結果が小さすぎて表現できない。 (この条件は現在サポートされていません。) |

構造体のメンバー **name** は、エラーの原因となった関数の名前を含む null で終わる文字列へのポインターです。 構造体のメンバー **arg1** と **arg2** は、エラーの原因となった値を指定します。 格納されている 1 つの引数を指定すると、もしも**arg1**します。

発生したエラーの既定の戻り値は **retval** です。 戻り値を変更する場合、戻り値はエラーが実際に発生したかどうかを指定する必要があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_matherr**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_matherr.c
/* illustrates writing an error routine for math
* functions. The error function must be:
*      _matherr
*/

#include <math.h>
#include <string.h>
#include <stdio.h>

int main()
{
    /* Do several math operations that cause errors. The _matherr
     * routine handles _DOMAIN errors, but lets the system handle
     * other errors normally.
     */
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );
}

/* Handle several math errors caused by passing a negative argument
* to log or log10 (_DOMAIN errors). When this happens, _matherr
* returns the natural or base-10 logarithm of the absolute value
* of the argument and suppresses the usual error message.
*/
int _matherr( struct _exception *except )
{
    /* Handle _DOMAIN errors for log or log10. */
    if( except->type == _DOMAIN )
    {
        if( strcmp( except->name, "log" ) == 0 )
        {
            except->retval = log( -(except->arg1) );
            printf( "Special: using absolute value: %s: _DOMAIN "
                     "error\n", except->name );
            return 1;
        }
        else if( strcmp( except->name, "log10" ) == 0 )
        {
            except->retval = log10( -(except->arg1) );
            printf( "Special: using absolute value: %s: _DOMAIN "
                     "error\n", except->name );
            return 1;
        }
    }
    printf( "Normal: " );
    return 0;    /* Else use the default actions */
}
```

```Output
Special: using absolute value: log: _DOMAIN error
log( -2.0 ) = 6.931472e-01
Special: using absolute value: log10: _DOMAIN error
log10( -5.0 ) = 6.989700e-01
Normal: log( 0.0 ) = -inf
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
