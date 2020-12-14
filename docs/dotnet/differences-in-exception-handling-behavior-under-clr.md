---
description: 詳細については、「/CLR での例外処理動作の相違点」を参照してください。
title: -CLR における例外処理動作の相違点
ms.date: 11/04/2016
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
ms.openlocfilehash: e7e07778e894448fea3d29acb3a32d71884be57c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252195"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>/CLR における例外処理動作の相違点

[マネージ例外の使用に関する基本的な概念では](../dotnet/basic-concepts-in-using-managed-exceptions.md) 、マネージアプリケーションの例外処理について説明します。 このトピックでは、例外処理の標準的な動作との違いといくつかの制限について詳しく説明します。 詳細については、「 [_Set_se_translator 関数](../c-runtime-library/reference/set-se-translator.md)」を参照してください。

## <a name="jumping-out-of-a-finally-block"></a><a name="vcconjumpingoutofafinallyblock"></a> Finally ブロックからジャンプする

ネイティブ C/c + + コードでは、構造化例外処理 (SEH) を使用して __ **finally** ブロックからジャンプすることはできますが、警告が生成されます。  [/Clr](../build/reference/clr-common-language-runtime-compilation.md)の下で、 **finally** ブロックからジャンプすると、エラーが発生します。

```cpp
// clr_exception_handling_4.cpp
// compile with: /clr
int main() {
   try {}
   finally {
      return 0;   // also fails with goto, break, continue
    }
}   // C3276
```

## <a name="raising-exceptions-within-an-exception-filter"></a><a name="vcconraisingexceptionswithinanexceptionfilter"></a> 例外フィルター内での例外の発生

マネージコード内の [例外フィルター](../cpp/writing-an-exception-filter.md) の処理中に例外が発生すると、例外がキャッチされ、フィルターが0を返すかのように処理されます。

これは、入れ子になった例外が発生したネイティブコードの動作とは異なり、 **EXCEPTION_RECORD** 構造の **exceptionrecord** フィールド ( [getexceptioninformation](/windows/win32/Debug/getexceptioninformation)によって返される) が設定され、 **exceptionrecord** フィールドは0x10 ビットを設定します。 次の例は、この動作の違いを示しています。

```cpp
// clr_exception_handling_5.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

#ifndef false
#define false 0
#endif

int *p;

int filter(PEXCEPTION_POINTERS ExceptionPointers) {
   PEXCEPTION_RECORD ExceptionRecord =
                     ExceptionPointers->ExceptionRecord;

   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {
      // not a nested exception, throw one
      *p = 0; // throw another AV
   }
   else {
      printf("Caught a nested exception\n");
      return 1;
    }

   assert(false);

   return 0;
}

void f(void) {
   __try {
      *p = 0;   // throw an AV
   }
   __except(filter(GetExceptionInformation())) {
      printf_s("We should execute this handler if "
                 "compiled to native\n");
    }
}

int main() {
   __try {
      f();
   }
   __except(1) {
      printf_s("The handler in main caught the "
               "exception\n");
    }
}
```

### <a name="output"></a>出力

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

## <a name="disassociated-rethrows"></a><a name="vccondisassociatedrethrows"></a> 関連付け解除の再スロー

**/clr** は、キャッチハンドラー以外での例外の再スローをサポートしていません (非関連付けの再スローと呼ばれます)。 この型の例外は、標準 C++ 再スローとして扱われます。 アクティブなマネージ例外があるときに、関連付けが解除された再スローが発生した場合は、例外が C++ 例外としてラップされ、再スローされます。 この型の例外は、型の例外としてのみキャッチでき <xref:System.Runtime.InteropServices.SEHException> ます。

次の例は、C++ 例外として再スローされるマネージ例外を示しています。

```cpp
// clr_exception_handling_6.cpp
// compile with: /clr
using namespace System;
#include <assert.h>
#include <stdio.h>

void rethrow( void ) {
   // This rethrow is a dissasociated rethrow.
   // The exception would be masked as SEHException.
   throw;
}

int main() {
   try {
      try {
         throw gcnew ApplicationException;
      }
      catch ( ApplicationException^ ) {
         rethrow();
         // If the call to rethrow() is replaced with
         // a throw statement within the catch handler,
         // the rethrow would be a managed rethrow and
         // the exception type would remain
         // System::ApplicationException
      }
   }

    catch ( ApplicationException^ ) {
      assert( false );

      // This will not be executed since the exception
      // will be masked as SEHException.
    }
   catch ( Runtime::InteropServices::SEHException^ ) {
      printf_s("caught an SEH Exception\n" );
    }
}
```

### <a name="output"></a>出力

```Output
caught an SEH Exception
```

## <a name="exception-filters-and-exception_continue_execution"></a><a name="vcconexceptionfiltersandexception_continue_execution"></a> 例外フィルターと EXCEPTION_CONTINUE_EXECUTION

フィルターがマネージアプリケーションで返された場合、フィルターは返された `EXCEPTION_CONTINUE_EXECUTION` ものとして扱われ `EXCEPTION_CONTINUE_SEARCH` ます。 これらの定数の詳細については、「 [try-Except ステートメント](../cpp/try-except-statement.md)」を参照してください。

次の例は、この違いを示しています。

```cpp
// clr_exception_handling_7.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

int main() {
   int Counter = 0;
   __try {
      __try  {
         Counter -= 1;
         RaiseException (0xe0000000|'seh',
                         0, 0, 0);
         Counter -= 2;
      }
      __except (Counter) {
         // Counter is negative,
         // indicating "CONTINUE EXECUTE"
         Counter -= 1;
      }
    }
    __except(1) {
      Counter -= 100;
   }

   printf_s("Counter=%d\n", Counter);
}
```

### <a name="output"></a>出力

```Output
Counter=-3
```

## <a name="the-_set_se_translator-function"></a><a name="vcconthe_set_se_translatorfunction"></a> _Set_se_translator 関数

の呼び出しによって設定された変換関数は、 `_set_se_translator` アンマネージコード内のキャッチにのみ影響します。 この制限の例を次に示します。

```cpp
// clr_exception_handling_8.cpp
// compile with: /clr /EHa
#include <iostream>
#include <windows.h>
#include <eh.h>
#pragma warning (disable: 4101)
using namespace std;
using namespace System;

#define MYEXCEPTION_CODE 0xe0000101

class CMyException {
public:
   unsigned int m_ErrorCode;
   EXCEPTION_POINTERS * m_pExp;

   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}

   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )
         : m_ErrorCode( i ), m_pExp( pExp ) {}

   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),
                                      m_pExp( c.m_pExp ) {}

   friend ostream& operator <<
                 ( ostream& out, const CMyException& inst ) {
      return out <<  "CMyException[\n" <<
             "Error Code: " << inst.m_ErrorCode <<  "]";
    }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {
   cout <<  "In my_trans_func.\n";
   throw CMyException( u, pExp );
}

#pragma managed
void managed_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );
   }
   catch ( CMyException x ) {}
   catch ( ... ) {
      printf_s("This is invoked since "
               "_set_se_translator is not "
               "supported when /clr is used\n" );
    }
}

#pragma unmanaged
void unmanaged_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE,
                      0, 0, 0 );
   }
   catch ( CMyException x ) {
      printf("Caught an SEH exception with "
             "exception code: %x\n", x.m_ErrorCode );
    }
    catch ( ... ) {}
}

// #pragma managed
int main( int argc, char ** argv ) {
   _set_se_translator( my_trans_func );

   // It does not matter whether the translator function
   // is registered in managed or unmanaged code
   managed_func();
   unmanaged_func();
}
```

### <a name="output"></a>出力

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>関連項目

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[MSVC での例外処理](../cpp/exception-handling-in-visual-cpp.md)
