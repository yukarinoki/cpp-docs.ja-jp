---
title: マルチ スレッドとロケール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19cc3817faab71c209586ad952162229f846e0a7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-and-locales"></a>マルチスレッドとロケール
C ランタイム ライブラリと、C++ 標準ライブラリの両方は、プログラムのロケールを変更するためのサポートを提供します。 このトピックでは、マルチ スレッド アプリケーションで両方のライブラリのロケール機能を使用するときに発生する問題について説明します。  
  
## <a name="remarks"></a>コメント  
 C ランタイム ライブラリを使用するマルチ スレッド アプリケーションを作成できます、`_beginthread`と`_beginthreadex`関数。 このトピックでは、これらの関数を使用して作成されたマルチ スレッド アプリケーションのみについて説明します。 詳細については、次を参照してください。 [_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)です。  
  
 C ランタイム ライブラリを使用してロケールを変更するには、使用、 [setlocale、_wsetlocale](../preprocessor/setlocale.md)関数。 以前のバージョンの Visual C では、この関数は常にアプリケーション全体のロケールを変更していました。 スレッドごとのロケールの設定を今すぐサポート。 これを使用して、 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)関数。 指定する[setlocale、_wsetlocale](../preprocessor/setlocale.md)のみ、現在のスレッドの呼び出しで指定したロケールを変更する必要があります`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`そのスレッドでします。 逆に、呼び出す`_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)`と、グローバルのロケールを使用するには、そのスレッドとすべての呼び出しに[setlocale、_wsetlocale](../preprocessor/setlocale.md)スレッドがスレッドごとのロケールを明示的に有効にしていないすべてのスレッドのロケールが変更されることです。  
  
 C ランタイム ライブラリを使用してロケールを変更するには、使用、 [locale クラス](../standard-library/locale-class.md)です。 呼び出して、 [locale::global](../standard-library/locale-class.md#global)メソッドが明示的に有効になっていないスレッドごとのロケールのすべてのスレッドのロケールを変更します。 1 つのスレッドまたはアプリケーションの部分で指定したロケールを変更するには、単のインスタンスを作成、`locale`そのスレッドまたはコードの一部のオブジェクト。  
  
> [!NOTE]
>  呼び出す[locale::global](../standard-library/locale-class.md#global) C++ 標準ライブラリと、C ランタイム ライブラリの両方のロケールを変更します。 ただし、呼び出し[setlocale、_wsetlocale](../preprocessor/setlocale.md)のみ、C ランタイム ライブラリ; C++ 標準ライブラリが影響を受けませんのロケールを変更します。  
  
 次の例を使用する方法を示して、 [setlocale、_wsetlocale](../preprocessor/setlocale.md) 、関数、 [locale クラス](../standard-library/locale-class.md)、および[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)内のアプリケーションのロケールを変更する関数複数の異なるシナリオです。  
  
## <a name="example"></a>例  
 この例では、メイン スレッドは、2 つの子のスレッドを生成します。 呼び出してスレッドごとのロケールにより、最初のスレッドでは、スレッド A、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`です。 2 番目のスレッド、スレッド B だけでなく、メイン スレッドには、スレッドごとのロケールが有効にしません。 スレッドのロケールを使用して、変更に A はそのが進みます、 [setlocale、_wsetlocale](../preprocessor/setlocale.md) C ランタイム ライブラリの関数。  
  
 以降、スレッド A は、スレッドごとのロケールが有効にすると、スレッド A スタート"french"ロケールを使用して C ランタイム ライブラリ関数のみを持っています。 C ランタイム ライブラリ関数、メイン スレッドとスレッド B では、"C"ロケールを使用し続けます。 また、 [setlocale、_wsetlocale](../preprocessor/setlocale.md) C++ 標準ライブラリのロケール、オブジェクトは、"C"ロケールを使用して引き続きすべての C++ 標準ライブラリには影響しません。  
  
```  
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
  
## <a name="example"></a>例  
 この例では、メイン スレッドは、2 つの子のスレッドを生成します。 呼び出してスレッドごとのロケールにより、最初のスレッドでは、スレッド A、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`です。 2 番目のスレッド、スレッド B だけでなく、メイン スレッドには、スレッドごとのロケールが有効にしません。 スレッドのロケールを使用して、変更に A はそのが進みます、 [locale::global](../standard-library/locale-class.md#global) C++ 標準ライブラリのメソッドです。  
  
 以降、スレッド A は、スレッドごとのロケールが有効にすると、スレッド A スタート"french"ロケールを使用して C ランタイム ライブラリ関数のみを持っています。 C ランタイム ライブラリ関数、メイン スレッドとスレッド B では、"C"ロケールを使用し続けます。 ただし、以降、 [locale::global](../standard-library/locale-class.md#global)メソッド ロケールを変更します「グローバル」、"french"ロケールを使用してすべてのスレッド内のすべての C++ 標準ライブラリ オブジェクトを開始します。  
  
```  
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
  
## <a name="example"></a>例  
 この例では、メイン スレッドは、2 つの子のスレッドを生成します。 呼び出してスレッドごとのロケールにより、最初のスレッドでは、スレッド A、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`です。 2 番目のスレッド、スレッド B だけでなく、メイン スレッドには、スレッドごとのロケールが有効にしません。 スレッド B 次に、ロケールを使用して、 [setlocale、_wsetlocale](../preprocessor/setlocale.md) C ランタイム ライブラリの関数。  
  
 スレッド B がスレッドごとのロケールが有効になっている必要があるない、ため、メイン スレッドとスレッド B では、C ランタイム ライブラリ関数は"french"ロケールを使用して開始します。 スレッド A があるスレッドごとのロケールが有効になっているために、"C"ロケールを使用するスレッド A 続行で C ランタイム ライブラリ関数。 また、 [setlocale、_wsetlocale](../preprocessor/setlocale.md) C++ 標準ライブラリのロケール、オブジェクトは、"C"ロケールを使用して引き続きすべての C++ 標準ライブラリには影響しません。  
  
```  
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
  
## <a name="example"></a>例  
 この例では、メイン スレッドは、2 つの子のスレッドを生成します。 呼び出してスレッドごとのロケールにより、最初のスレッドでは、スレッド A、`_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`です。 2 番目のスレッド、スレッド B だけでなく、メイン スレッドには、スレッドごとのロケールが有効にしません。 スレッド B 次に、ロケールを使用して、 [locale::global](../standard-library/locale-class.md#global) C++ 標準ライブラリのメソッドです。  
  
 スレッド B がスレッドごとのロケールが有効になっている必要があるない、ため、メイン スレッドとスレッド B では、C ランタイム ライブラリ関数は"french"ロケールを使用して開始します。 スレッド A があるスレッドごとのロケールが有効になっているために、"C"ロケールを使用するスレッド A 続行で C ランタイム ライブラリ関数。 ただし、以降、 [locale::global](../standard-library/locale-class.md#global)メソッド ロケールを変更します「グローバル」、"french"ロケールを使用してすべてのスレッド内のすべての C++ 標準ライブラリ オブジェクトを開始します。  
  
```  
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
 [古いコード (Visual C) のためのマルチ スレッド処理のサポート](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [国際化](../c-runtime-library/internationalization.md)   
 [ロケール](../c-runtime-library/locale.md)   
 [\<clocale >](../standard-library/clocale.md)   
 [\<locale>](../standard-library/locale.md)   
 [locale クラス](../standard-library/locale-class.md)