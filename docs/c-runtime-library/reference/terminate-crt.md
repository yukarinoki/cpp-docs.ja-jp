---
title: terminate (CRT)
ms.date: 4/2/2020
api_name:
- terminate
- _o_terminate
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- terminate
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
ms.openlocfilehash: 1ec4e27096dd6b5fea089e21c95022542d7adc82
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912221"
---
# <a name="terminate-crt"></a>terminate (CRT)

**Set_terminate**を使用して、 [abort](abort.md)または指定した関数を呼び出します。

## <a name="syntax"></a>構文

```C
void terminate( void );
```

## <a name="remarks"></a>解説

**Terminate**関数は、C++ 例外処理で使用され、次の場合に呼び出されます。

- スローされた C++ 例外と一致する catch ハンドラーが見つからない。

- スタック アンワインド中にデストラクター関数によって例外がスローされた。

- 例外をスローした後でスタックが破損した。

**terminate**呼び出しは、既定で[中止](abort.md)されます。 独自の終了関数を記述し、関数の名前を引数として**set_terminate**を呼び出すことによって、この既定値を変更できます。 **terminate**は、 **set_terminate**の引数として渡された最後の関数を呼び出します。 詳細については、「[Unhandled C++ Exceptions](../../cpp/unhandled-cpp-exceptions.md)」(ハンドルされない C++ 例外) を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**解約**|\<eh.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```cpp
// crt_terminate.cpp
// compile with: /EHsc
#include <eh.h>
#include <process.h>
#include <iostream>
using namespace std;

void term_func();

int main()
{
    int i = 10, j = 0, result;
    set_terminate( term_func );
    try
    {
        if( j == 0 )
            throw "Divide by zero!";
        else
            result = i/j;
    }
    catch( int )
    {
        cout << "Caught some integer exception.\n";
    }
    cout << "This should never print.\n";
}

void term_func()
{
    cout << "term_func() was called by terminate().\n";

    // ... cleanup tasks performed here

    // If this function does not exit, abort is called.

    exit(-1);
}
```

```Output
term_func() was called by terminate().
```

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[取り消し](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[不適切](unexpected-crt.md)<br/>
