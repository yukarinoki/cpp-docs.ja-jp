---
title: _set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler
ms.date: 4/2/2020
api_name:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
- _o__set_invalid_parameter_handler
- _o__set_thread_local_invalid_parameter_handler
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
- set_invalid_parameter_handler
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
ms.openlocfilehash: 0637937d4596d28875c40efec62f79a32f533dcf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337676"
---
# <a name="_set_invalid_parameter_handler-_set_thread_local_invalid_parameter_handler"></a>_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler

CRT が無効な引数を検出したときに呼び出される関数を設定します。

## <a name="syntax"></a>構文

```C
_invalid_parameter_handler _set_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
```

### <a name="parameters"></a>パラメーター

*p新しい*<br/>
新しい無効なパラメーター ハンドラーへの関数ポインターです。

## <a name="return-value"></a>戻り値

呼び出し前の無効なパラメーター ハンドラーへのポインターです。

## <a name="remarks"></a>解説

多くの C ランタイム関数では、渡された引数の有効性を確認しています。 無効な引数が渡された場合、この関数は**errno**エラー番号を設定するか、エラー コードを返します。 このような場合、無効なパラメーター ハンドラーも呼び出されます。 C ランタイムでは、プログラムを終了してランタイム エラー メッセージを表示する、既定のグローバルの無効なパラメーター ハンドラーを提供しています。 **_set_invalid_parameter_handler**を使用して、独自の関数をグローバル無効なパラメーター ハンドラーとして設定できます。 C ランタイムでは、スレッド ローカルの無効なパラメーター ハンドラーもサポートしています。 _set_thread_local_invalid_parameter_handler**を使用**してスレッド内でスレッドローカル パラメータ ハンドラを設定する場合、そのスレッドから呼び出される C ランタイム関数は、グローバル ハンドラの代わりにそのハンドラを使用します。 グローバルの無効な引数ハンドラーとしては、同時に 1 つの関数しか指定できません。 1 つのスレッド内では 1 つの関数しかスレッド ローカルの無効な引数ハンドラーとして指定できませんが、別のスレッドでは別のスレッド ローカルなハンドラーを持つことができます。 これにより、コードの一部で使用するハンドラーを、他のスレッドの動作に影響を与えずに変更できます。

通常、ランタイムが無効なパラメーター関数を呼び出したということは、回復不可能なエラーが発生したことを意味します。 提供する無効なパラメーター ハンドラー関数は、保存できるデータを保存してから中止処理をしなければなりません。 エラーが回復可能であるという確信を持てない限り、main 関数に制御を返すべきではありません。

無効なパラメーター ハンドラー関数には以下のプロトタイプが必要です。

```C
void _invalid_parameter(
   const wchar_t * expression,
   const wchar_t * function,
   const wchar_t * file,
   unsigned int line,
   uintptr_t pReserved
);
```

*expression*引数は、エラーを発生させた引数式のワイド文字列表現です。 *関数*の引数は、無効な引数を受け取った CRT 関数の名前です。 *file*引数は、関数を含む CRT ソース ファイルの名前です。 *行*引数は、そのファイル内の行番号です。 最後の引数は予約済みです。 CRT ライブラリのデバッグ バージョンを使用しない限り、パラメーターはすべて**NULL 値**になります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> または \<stdlib.h>|

**_set_invalid_parameter_handler**および **_set_thread_local_invalid_parameter_handler**機能は、マイクロソフト固有のものです。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

次の例では、無効なパラメーターを受け取った関数および CRT ソースのファイル名と行番号を出力するために、無効なパラメーター エラー ハンドラーが使用されています。 デバッグ CRT ライブラリを使用した場合、無効なパラメーター エラーによってアサーションも発生しますが、この例では [_CrtSetReportMode](crtsetreportmode.md) を使用してアサーションが無効化されています。

```C
// crt_set_invalid_parameter_handler.c
// compile with: /Zi /MTd
#include <stdio.h>
#include <stdlib.h>
#include <crtdbg.h>  // For _CrtSetReportMode

void myInvalidParameterHandler(const wchar_t* expression,
   const wchar_t* function,
   const wchar_t* file,
   unsigned int line,
   uintptr_t pReserved)
{
   wprintf(L"Invalid parameter detected in function %s."
            L" File: %s Line: %d\n", function, file, line);
   wprintf(L"Expression: %s\n", expression);
   abort();
}

int main( )
{
   char* formatString;

   _invalid_parameter_handler oldHandler, newHandler;
   newHandler = myInvalidParameterHandler;
   oldHandler = _set_invalid_parameter_handler(newHandler);

   // Disable the message box for assertions.
   _CrtSetReportMode(_CRT_ASSERT, 0);

   // Call printf_s with invalid parameters.

   formatString = NULL;
   printf(formatString);
}
```

```Output
Invalid parameter detected in function common_vfprintf. File: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Line: 32
Expression: format != nullptr
```

## <a name="see-also"></a>関連項目

[_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[CRT 関数のセキュリティ強化バージョン](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
