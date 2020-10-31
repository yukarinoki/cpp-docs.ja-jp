---
title: _configthreadlocale
ms.date: 10/29/2020
description: '`_configthreadlocale`スレッドごとのロケールオプションを構成するために使用される Microsoft C ランタイム関数について説明します。'
api_name:
- _configthreadlocale
- _o__configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _configthreadlocale
- configthreadlocale
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
ms.openlocfilehash: 3ffea30f8547088d6117ee980cdf28f017e87e83
ms.sourcegitcommit: 868838273eda35eb72c78dccf4121940dcc04706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "93102325"
---
# `_configthreadlocale`

スレッドごとのロケール オプションを設定します。

## <a name="syntax"></a>構文

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>パラメーター

*`per_thread_locale_type`*\
設定する値。 次の一覧に示すオプションのいずれかを指定します。

## <a name="return-value"></a>戻り値

前のスレッドごとのロケールの状態 ( **`_DISABLE_PER_THREAD_LOCALE`** または **`_ENABLE_PER_THREAD_LOCALE`** )、または失敗した場合は-1。

## <a name="remarks"></a>注釈

関数は、 **`_configthreadlocale`** スレッド固有のロケールの使用を制御するために使用されます。 *`per_thread_locale_type`* スレッドごとのロケールの状態を指定または確認するには、次のいずれかのオプションを使用します。

| オプション | 説明 |
|-|-|
| **`_ENABLE_PER_THREAD_LOCALE`** | 現在のスレッドでスレッド固有のロケールを使用させます。 このスレッドでの後続の呼び出しは **`setlocale`** 、スレッド独自のロケールだけに影響します。 |
| **`_DISABLE_PER_THREAD_LOCALE`** | 現在のスレッドでグローバルなロケールを使用させます。 **`setlocale`** このスレッドでの後続の呼び出しは、グローバルロケールを使用する他のスレッドに影響します。 |
| **0** | この特定のスレッドの現在の設定を取得します。 |

これらの関数は、、、、およびの動作に影響し **`setlocale`** **`_tsetlocale`** **`_wsetlocale`** **`_setmbcp`** ます。 スレッドごとのロケールが無効になっている場合、またはの後続の呼び出しで **`setlocale`** は、 **`_wsetlocale`** グローバルロケールを使用するすべてのスレッドのロケールが変更されます。 スレッドごとのロケールが有効な場合、 **`setlocale`** またはは **`_wsetlocale`** 現在のスレッドのロケールにのみ影響します。

を使用し **`_configthreadlocale`** てスレッドごとのロケールを有効にする場合 **`setlocale`** は、その後すぐにまたはを呼び出して、 **`_wsetlocale`** そのスレッドで優先ロケールを設定することをお勧めします。

が *`per_thread_locale_type`* 表に示されている値のいずれでもない場合、この関数は「 [パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は **`errno`** をに設定 **`EINVAL`** し、-1 を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`_configthreadlocale`**|\`<locale .h>'|

## <a name="example"></a>例

```cpp
// crt_configthreadlocale.cpp
//
// This program demonstrates the use of _configthreadlocale when
// using two independent threads.
//
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp

#include <locale.h>
#include <mbctype.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date and time in the current
// locale's format.
int get_time(unsigned char* str)
{
    __time64_t  ltime;
    struct tm   thetime;

    // Retieve the time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // using %#x is the long date representation,
    // appropriate to the current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm*)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to German
// and prints the time.
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )
{
    unsigned char str[BUFF_SIZE];

    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the thread code page
    _setmbcp(_MB_CP_ANSI);

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "German"));

    // Retrieve the time string from the helper function
    if (get_time(str) == 0)
    {
        printf("The time in German locale is: '%s'\n", str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread spawns a second thread (above) and then
// sets the locale to English and prints the time.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Retrieve the time string from the helper function
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "English"));

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      NULL, 0, &threadID );

    if (get_time(str) == 0)
    {
        // Retrieve the time string from the helper function
        printf("The time in English locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to English_United States.1252.
The time in English locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to German_Germany.1252.
The time in German locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>関連項目

[`setlocale`, `_wsetlocale`](setlocale-wsetlocale.md)\
[`_beginthread`, `_beginthreadex`](beginthread-beginthreadex.md)\
[国](../../c-runtime-library/locale.md)\
[マルチスレッドとロケール](../../parallel/multithreading-and-locales.md)
