---
title: 例外処理 (C/C++) の構造 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1edcf2cb24273f475b1ba98e5e973f5704c0cec8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461703"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)
Windows および Visual C++ は構造化例外処理 (SEH) をサポートしていますが、コードの移植性と柔軟性が高くなる ISO 標準の C++ 例外処理を使用することをお勧めします。 ただし、既存のコードや特定の種類のプログラムでは、SEH を使用する必要がある場合もあります。  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
  
## <a name="grammar"></a>文法  
 *try-ステートメントを除く*:  
  
 `__try` *複合ステートメント*  
  
 `__except` ( `expression` )*複合ステートメント*  
  
## <a name="remarks"></a>Remarks  
 SEH を使うと、実行が予期せずに終了した場合にメモリ ブロックやファイルなどのリソースが適切であることを確認できます。 特定の問題を処理することもできます。-メモリの不足など — に依存しない簡潔の構造化されたコードを使用して**goto**ステートメントやリターン コードの複雑なテスト。  
  
 ここで説明する try-except および try-finally ステートメントは C 言語に対する Microsoft の拡張機能です。 これらは、イベント後にプログラムの制御をアプリケーションが取得するようにし、そうでない場合は実行を終了させることによって SEH をサポートします。 SEH は C++ ソース ファイルと連携しますが、C++ 向けに設計されていません。 使用してコンパイルする C++ プログラムで SEH を使用するかどうか、 [/EH](../build/reference/eh-exception-handling-model.md)オプション-特定の修飾子と共に、ローカル オブジェクトのデストラクターが呼び出されますが、その他の実行動作が期待どおりではありません。 (概要については、この記事で後述する例を参照してください)。ほとんどの場合、SEH の代わりに勧め ISO 標準を使用する[C++ 例外処理](../cpp/try-throw-and-catch-statements-cpp.md)、Visual C もサポートします。 C++ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。  
  
 SEH を使用する C モジュールがある場合、C++ 例外処理を使用する C++ モジュールとそれらを混在させることができます。 詳しくは、次を参照してください。[例外処理の相違点](../cpp/exception-handling-differences.md)します。  
  
 SEH メカニズムには次の 2 つがあります。  
  
-   [例外ハンドラー](../cpp/writing-an-exception-handler.md)に応答したり、例外を無視することができます。  
  
-   [終了ハンドラー](../cpp/writing-a-termination-handler.md)例外のコード ブロックの終了の原因とすると呼ばれます。  
  
 これら 2 種類のハンドラーは区別されますが、"スタックのアンワインド" というプロセスを通じて密接に関係しています。 例外が発生すると、Windows は現在アクティブである最も新しくインストールされた例外ハンドラーを検索します。 ハンドラーは、次の 3 つのうちの 1 つを行うことができます。  
  
-   例外の認識に失敗し、他のハンドラーに制御を渡す。  
  
-   例外を認識し、拒絶する。  
  
-   例外を認識し、処理する。  
  
 例外を認識する例外ハンドラーは、例外が発生したときに実行中だった関数内にない場合があります。 場合によっては、スタックのかなり上位の関数内にあります。 現在実行中の関数と、スタック フレーム上の他のすべての関数が終了します。 このプロセス中にスタックでない"アンワインド"されます。 終了した関数のローカル変数は、-でない限り**静的**: スタックから消去されます。  
  
 これがスタックをアンワインドするため、オペレーティング システムは、各関数に書き込んだ終了ハンドラーを呼び出します。 終了ハンドラーを使用して、異常終了のために開いたままになっているリソースをクリーンアップできます。 クリティカル セクションに入った場合、終了ハンドラーで終了できます。 プログラムがシャットダウンする場合、一時ファイルを閉じたり削除するなどの他のハウスキーピング タスクを実行できます。  
  
 詳細については次を参照してください:  
  
-   [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)  
  
-   [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)  
  
-   [C++ での構造化例外処理の使用](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## <a name="example"></a>例  
 前に説明したように、C++ プログラムで SEH を使用し、特定の修飾子 (たとえば `/EH` や `/EHsc`) と共に `/EHa` オプションを使用してコンパイルすると、ローカル オブジェクトのデストラクターが呼び出されます。 ただし、C++ 例外も使用している場合は、実行時の動作は予期したとおりにならない可能性があります。 次の例は、これらの動作の違いを示しています。  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
```  
  
 使用する場合 **/EHsc**このコードがローカル テストのコントロールをコンパイルする`CPPEX`が未定義の場合がありますの実行はされず、`TestClass`デストラクターと出力は次のように。  
  
```Output  
Triggering SEH exception  
Executing SEH __except block  
```  
  
 使用する場合 **/EHsc**コードをコンパイルして`CPPEX`によって定義されている`/DCPPEX`(C++ 例外をスロー) するため、`TestClass`デストラクターが実行され、出力は次のようになります。  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 使用する場合 **/EHa** 、コードをコンパイルする、`TestClass`デストラクターの実行を使用して例外がスローされたかどうかに関係なく`std::throw`または SEH を使用して例外をトリガーする (`CPPEX`かどうかを定義)。 出力は次のようになります。  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 詳細については、「[/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)」を参照してください。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [\<exception>](../standard-library/exception.md)   
 [エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [構造化例外処理 (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)