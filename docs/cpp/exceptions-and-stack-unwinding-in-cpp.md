---
title: C++ での例外とスタック アンワインド
ms.date: 11/19/2019
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
ms.openlocfilehash: 11657206e86dbc81eb62c1e11b49fd87777f11d8
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246568"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++ での例外とスタック アンワインド

C++ 例外の機能では、制御は throw ステートメントから、スローされる型を処理できる最初の catch ステートメントに移動します。 When the catch statement is reached, all of the automatic variables that are in scope between the throw and catch statements are destroyed in a process that is known as *stack unwinding*. スタック アンワインドでは、次のように実行されます。

1. Control reaches the **try** statement by normal sequential execution. The guarded section in the **try** block is executed.

1. If no exception is thrown during execution of the guarded section, the **catch** clauses that follow the **try** block are not executed. Execution continues at the statement after the last **catch** clause that follows the associated **try** block.

1. If an exception is thrown during execution of the guarded section or in any routine that the guarded section calls either directly or indirectly, an exception object is created from the object that is created by the **throw** operand. (This implies that a copy constructor may be involved.) At this point, the compiler looks for a **catch** clause in a higher execution context that can handle an exception of the type that is thrown, or for a **catch** handler that can handle any type of exception. The **catch** handlers are examined in order of their appearance after the **try** block. If no appropriate handler is found, the next dynamically enclosing **try** block is examined. This process continues until the outermost enclosing **try** block is examined.

1. 一致するハンドラーが見つからない場合、またはアンワインド処理中に例外が発生した場合でも、ハンドラーが制御を取得する前であれば、定義済みのランタイム関数 `terminate` が呼び出されます。 例外がスローされた後でも、アンワインドが開始される前に例外が発生した場合は、`terminate` が呼び出されます。

1. If a matching **catch** handler is found, and it catches by value, its formal parameter is initialized by copying the exception object. 参照によってキャッチする場合、例外オブジェクトを示すためにパラメーターが初期化されます。 正式なパラメーターが初期化されると、スタックをアンワインドするプロセスが開始されます。 This involves the destruction of all automatic objects that were fully constructed—but not yet destructed—between the beginning of the **try** block that is associated with the **catch** handler and the throw site of the exception. 破棄は、構築の逆順に発生します。 The **catch** handler is executed and the program resumes execution after the last handler—that is, at the first statement or construct that is not a **catch** handler. Control can only enter a **catch** handler through a thrown exception, never through a **goto** statement or a **case** label in a **switch** statement.

## <a name="stack-unwinding-example"></a>Stack unwinding example

次の例では、例外がスローされたときにスタックをアンワインドする方法を示します。 スレッド上で実行すると、`C` の throw ステートメントから `main` の catch ステートメントにジャンプし、その途中の各関数をアンワインドします。 `Dummy` オブジェクトが作成され、スコープ外として破棄される順序に注意してください。 関数が catch ステートメントを含む `main` なしで完了しないことにも注意してください。 関数 `A` はその `B()` の呼び出しから戻りません。`B` はその `C()` の呼び出しから戻りません。 `Dummy` ポインターの定義と対応する DELETE ステートメントをコメントから外してプログラムを実行すると、ポインターは削除されなくなります。 これは、関数が例外の保証を提供しない場合に発生することがある問題を示しています。 詳細については、「方法: 例外に対してデザインする」を参照してください。 catch ステートメントをコメント アウトすると、未処理の例外によってプログラムが終了するときの動作が示されます。

```cpp
#include <string>
#include <iostream>
using namespace std;

class MyException{};
class Dummy
{
    public:
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }
    string MyName;
    int level;
};

void C(Dummy d, int i)
{
    cout << "Entering FunctionC" << endl;
    d.MyName = " C";
    throw MyException();

    cout << "Exiting FunctionC" << endl;
}

void B(Dummy d, int i)
{
    cout << "Entering FunctionB" << endl;
    d.MyName = "B";
    C(d, i + 1);
    cout << "Exiting FunctionB" << endl;
}

void A(Dummy d, int i)
{
    cout << "Entering FunctionA" << endl;
    d.MyName = " A" ;
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!
    B(d, i + 1);
 //   delete pd;
    cout << "Exiting FunctionA" << endl;
}

int main()
{
    cout << "Entering main" << endl;
    try
    {
        Dummy d(" M");
        A(d,1);
    }
    catch (MyException& e)
    {
        cout << "Caught an exception of type: " << typeid(e).name() << endl;
    }

    cout << "Exiting main." << endl;
    char c;
    cin >> c;
}

/* Output:
    Entering main
    Created Dummy: M
    Copy created Dummy: M
    Entering FunctionA
    Copy created Dummy: A
    Entering FunctionB
    Copy created Dummy: B
    Entering FunctionC
    Destroyed Dummy: C
    Destroyed Dummy: B
    Destroyed Dummy: A
    Destroyed Dummy: M
    Caught an exception of type: class MyException
    Exiting main.

*/
```
