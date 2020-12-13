---
description: 詳細については、「マルチスレッドとロケール」を参照してください。
title: マルチスレッドとロケール
ms.date: 11/04/2016
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
ms.openlocfilehash: 246eb6c9be7046a77770de701d15754579b66055
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149982"
---
# <a name="multithreading-and-locales"></a>マルチスレッドとロケール

C ランタイムライブラリと C++ 標準ライブラリは両方とも、プログラムのロケールの変更をサポートしています。 このトピックでは、マルチスレッドアプリケーションで両方のライブラリのロケール機能を使用するときに発生する問題について説明します。

## <a name="remarks"></a>解説

C ランタイムライブラリでは、関数と関数を使用してマルチスレッドアプリケーションを作成でき `_beginthread` `_beginthreadex` ます。 このトピックでは、これらの関数を使用して作成されたマルチスレッドアプリケーションのみを取り上げます。 詳細については、「 [_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)」を参照してください。

C ランタイムライブラリを使用してロケールを変更するには、 [setlocale](../preprocessor/setlocale.md) 関数を使用します。 以前のバージョンの Visual C++ では、この関数は常に、アプリケーション全体にわたってロケールを変更します。 スレッドごとのロケールの設定がサポートされるようになりました。 これを行うには、 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 関数を使用します。 [Setlocale](../preprocessor/setlocale.md)が現在のスレッドのロケールのみを変更するように指定するには、 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` そのスレッドでを呼び出します。 逆に、を呼び出すと、 `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` そのスレッドはグローバルロケールを使用し、そのスレッドの [setlocale](../preprocessor/setlocale.md) を呼び出すと、スレッドごとのロケールを明示的に有効にしていないすべてのスレッドのロケールが変更されます。

C++ ランタイムライブラリを使用してロケールを変更するには、 [Locale クラス](../standard-library/locale-class.md)を使用します。 [Locale:: global](../standard-library/locale-class.md#global)メソッドを呼び出すことによって、スレッドごとのロケールを明示的に有効にしていないすべてのスレッドでロケールを変更します。 1つのスレッドまたはアプリケーションの一部でロケールを変更するには、 `locale` そのスレッドまたはコードの一部にオブジェクトのインスタンスを作成するだけです。

> [!NOTE]
> [Locale:: global](../standard-library/locale-class.md#global)を呼び出すと、C++ 標準ライブラリと c ランタイムライブラリの両方のロケールが変更されます。 ただし、 [setlocale](../preprocessor/setlocale.md) を呼び出すと、C ランタイムライブラリのロケールのみが変更されます。C++ 標準ライブラリは影響を受けません。

次の例は、 [setlocale](../preprocessor/setlocale.md) 関数、 [locale クラス](../standard-library/locale-class.md)、および [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 関数を使用して、いくつかの異なるシナリオでアプリケーションのロケールを変更する方法を示しています。

## <a name="example-change-locale-with-per-thread-locale-enabled"></a>例: スレッドごとのロケールが有効になっているロケールを変更する

この例では、メインスレッドによって2つの子スレッドが生成されます。 最初のスレッド (スレッド A) は、を呼び出すことにより、スレッドごとのロケールを有効にし `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` ます。 2番目のスレッドであるスレッド B とメインスレッドは、スレッドごとのロケールを有効にしません。 次に、C ランタイムライブラリの [setlocale](../preprocessor/setlocale.md) 関数を使用して、スレッド A がロケールの変更に進みます。

スレッド A にはスレッドごとのロケールが有効になっているため、スレッド A の C ランタイムライブラリ関数のみが "フランス語" ロケールを使用して開始されます。 スレッド B の C ランタイムライブラリ関数とメインスレッドでは、"C" ロケールが引き続き使用されます。 また、 [setlocale](../preprocessor/setlocale.md) は C++ 標準ライブラリのロケールには影響しないため、すべての C++ 標準ライブラリオブジェクトは引き続き "C" ロケールを使用します。

```cpp
// multithread_locale_1.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "C"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "C"
```

## <a name="example-change-global-locale-with-per-thread-locale-enabled"></a>例: スレッドごとのロケールが有効になっているグローバルロケールを変更する

この例では、メインスレッドによって2つの子スレッドが生成されます。 最初のスレッド (スレッド A) は、を呼び出すことにより、スレッドごとのロケールを有効にし `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` ます。 2番目のスレッドであるスレッド B とメインスレッドは、スレッドごとのロケールを有効にしません。 次に、スレッド A は、C++ 標準ライブラリの [locale:: global](../standard-library/locale-class.md#global) メソッドを使用してロケールを変更します。

スレッド A にはスレッドごとのロケールが有効になっているため、スレッド A の C ランタイムライブラリ関数のみが "フランス語" ロケールを使用して開始されます。 スレッド B の C ランタイムライブラリ関数とメインスレッドでは、"C" ロケールが引き続き使用されます。 ただし、 [locale:: global](../standard-library/locale-class.md#global) メソッドによってロケールが "グローバル" に変更されるため、すべてのスレッド内のすべての C++ 標準ライブラリオブジェクトは、"フランス語" ロケールの使用を開始します。

```cpp
// multithread_locale_2.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "French_France.1252"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="example-change-locale-without-per-thread-locale-enabled"></a>例: スレッドごとのロケールを有効にしないでロケールを変更する

この例では、メインスレッドによって2つの子スレッドが生成されます。 最初のスレッド (スレッド A) は、を呼び出すことにより、スレッドごとのロケールを有効にし `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` ます。 2番目のスレッドであるスレッド B とメインスレッドは、スレッドごとのロケールを有効にしません。 次に、C ランタイムライブラリの [setlocale](../preprocessor/setlocale.md) 関数を使用して、スレッド B がロケールの変更に進みます。

スレッド B ではスレッドごとのロケールが有効になっていないため、スレッド B の C ランタイムライブラリ関数とメインスレッドでは、"フランス語" ロケールの使用が開始されます。 スレッド a にはスレッドごとのロケールが有効になっているため、スレッド A の C ランタイムライブラリ関数では、"C" ロケールが引き続き使用されます。 また、 [setlocale](../preprocessor/setlocale.md) は C++ 標準ライブラリのロケールには影響しないため、すべての C++ 標準ライブラリオブジェクトは引き続き "C" ロケールを使用します。

```cpp
// multithread_locale_3.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "C"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "C"
```

## <a name="example-change-global-locale-without-per-thread-locale-enabled"></a>例: スレッドごとのロケールを有効にせずにグローバルロケールを変更する

この例では、メインスレッドによって2つの子スレッドが生成されます。 最初のスレッド (スレッド A) は、を呼び出すことにより、スレッドごとのロケールを有効にし `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` ます。 2番目のスレッドであるスレッド B とメインスレッドは、スレッドごとのロケールを有効にしません。 次に、スレッド B は、C++ 標準ライブラリの [locale:: global](../standard-library/locale-class.md#global) メソッドを使用してロケールを変更します。

スレッド B ではスレッドごとのロケールが有効になっていないため、スレッド B の C ランタイムライブラリ関数とメインスレッドでは、"フランス語" ロケールの使用が開始されます。 スレッド a にはスレッドごとのロケールが有効になっているため、スレッド A の C ランタイムライブラリ関数では、"C" ロケールが引き続き使用されます。 ただし、 [locale:: global](../standard-library/locale-class.md#global) メソッドによってロケールが "グローバル" に変更されるため、すべてのスレッド内のすべての C++ 標準ライブラリオブジェクトは、"フランス語" ロケールの使用を開始します。

```cpp
// multithread_locale_4.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "French_France.1252"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="see-also"></a>関連項目

[旧形式のコードのためのマルチスレッド サポート (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)<br/>
[_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)<br/>
[setlocale](../preprocessor/setlocale.md)<br/>
[国際化](../c-runtime-library/internationalization.md)<br/>
[ロケール](../c-runtime-library/locale.md)<br/>
[\<clocale>](../standard-library/clocale.md)<br/>
[\<locale>](../standard-library/locale.md)<br/>
[locale クラス](../standard-library/locale-class.md)
