---
title: _configthreadlocale
ms.date: 11/04/2016
apiname:
- _configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 99e10a0330ba4880ea181e9fe3d56f3fb6bd6493
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340262"
---
# <a name="configthreadlocale"></a>_configthreadlocale

スレッドごとのロケール オプションを設定します。

## <a name="syntax"></a>構文

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>パラメーター

*per_thread_locale_type*<br/>
設定する値。 次の一覧に示すオプションのいずれかを指定します。

## <a name="return-value"></a>戻り値

前のスレッドごとのロケールの状態 (**_DISABLE_PER_THREAD_LOCALE**または **_ENABLE_PER_THREAD_LOCALE**)、または-1 を返します。

## <a name="remarks"></a>Remarks

**_Configurethreadlocale**スレッド固有のロケールの使用を制御する関数を使用します。 次のいずれかを使用して、 *per_thread_locale_type*オプションを指定またはスレッドごとのロケールの状態を確認します。

| オプション | 説明 |
|-|-|
| **_ENABLE_PER_THREAD_LOCALE** | 現在のスレッドでスレッド固有のロケールを使用させます。 後続の呼び出し**setlocale**このスレッドでスレッドのロケールだけに影響します。 |
| **_DISABLE_PER_THREAD_LOCALE** | 現在のスレッドでグローバルなロケールを使用させます。 後続の呼び出し**setlocale**このスレッドでグローバル ロケールを使用して他のスレッドに影響します。 |
| **0** | この特定のスレッドの現在の設定を取得します。 |

これらの関数の動作に影響を与える**setlocale**、 **_tsetlocale**、 **_wsetlocale**、および **_setmbcp**します。 スレッドごとのロケールが無効になっている、その後の呼び出しの場合**setlocale**または **_wsetlocale**グローバル ロケールを使用するすべてのスレッドのロケールを変更します。 スレッドごとのロケールを有効にすると、 **setlocale**または **_wsetlocale**現在のスレッドのロケールにのみ影響します。

使用する場合 **_configurethreadlocale**呼び出すことが推奨スレッドごとのロケールを有効にする**setlocale**または **_wsetlocale**そのスレッドで優先ロケールを設定するにはその後すぐにします。

場合*per_thread_locale_type*が、値の 1 つの表に示す、この関数は無効なパラメーター ハンドラーを呼び出します」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL** -1 を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_configthreadlocale**|\<locale.h>|

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

[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[_beginthread、_beginthreadex](beginthread-beginthreadex.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチスレッドとロケール](../../parallel/multithreading-and-locales.md)<br/>
