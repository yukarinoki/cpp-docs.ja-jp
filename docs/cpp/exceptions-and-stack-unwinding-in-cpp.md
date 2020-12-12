---
description: 詳細については、「C++ での例外とスタックアンワインド」を参照してください。
title: C++ での例外とスタック アンワインド
ms.date: 11/19/2019
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
ms.openlocfilehash: 4f9c5faff4dafcae41831eb4b24345134912b073
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164784"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++ での例外とスタック アンワインド

C++ 例外の機能では、制御は throw ステートメントから、スローされる型を処理できる最初の catch ステートメントに移動します。 Catch ステートメントに到達すると、throw ステートメントと catch ステートメントの間のスコープ内にあるすべての自動変数は、 *スタックアンワインド* と呼ばれるプロセスで破棄されます。 スタック アンワインドでは、次のように実行されます。

1. 制御は、 **`try`** 通常の順次実行によってステートメントに到達します。 ブロック内の保護されたセクション **`try`** が実行されます。

1. 保護されたセクションの実行中に例外がスローされない場合、 **`catch`** ブロックに続く句は実行され **`try`** ません。 実行は、 **`catch`** 関連付けられたブロックの後にある最後の句の後のステートメントから続行され **`try`** ます。

1. 保護されたセクションの実行中、または保護されたセクションが直接または間接的に呼び出したルーチンで例外がスローされた場合は、オペランドによって作成されたオブジェクトから例外オブジェクトが作成され **`throw`** ます。 (これは、コピーコンストラクターが関係している可能性があることを意味します)。この時点で、コンパイラは、 **`catch`** スローされた型の例外、または **`catch`** 任意の種類の例外を処理できるハンドラーに対して、より高い実行コンテキストで句を検索します。 ハンドラーは、 **`catch`** ブロックの後に表示され **`try`** ます。 適切なハンドラーが見つからない場合は、次に動的に囲む **`try`** ブロックが検査されます。 このプロセスは、最も外側の **`try`** ブロックが検査されるまで続行されます。

1. 一致するハンドラーが見つからない場合、またはアンワインド処理中に例外が発生した場合でも、ハンドラーが制御を取得する前であれば、定義済みのランタイム関数 `terminate` が呼び出されます。 例外がスローされた後でも、アンワインドが開始される前に例外が発生した場合は、`terminate` が呼び出されます。

1. 一致する **`catch`** ハンドラーが見つかり、値渡しでキャッチした場合、その仮パラメーターは例外オブジェクトをコピーすることによって初期化されます。 参照によってキャッチする場合、例外オブジェクトを示すためにパラメーターが初期化されます。 正式なパラメーターが初期化されると、スタックをアンワインドするプロセスが開始されます。 これには、 **`try`** ハンドラーに関連付けられているブロックの先頭 **`catch`** と例外の throw サイトの間で完全に構築されているが、まだ破棄されていないすべての自動オブジェクトが破棄されます。 破棄は、構築の逆順に発生します。 **`catch`** ハンドラーが実行され、最後のハンドラー (つまり、ハンドラーではない最初のステートメントまたはコンストラクト) の後にプログラムが実行を再開し **`catch`** ます。 コントロールは、スローさ **`catch`** れた例外を通じてのみハンドラーに入力でき **`goto`** ます。ステートメントまたは **`case`** ステートメント内のラベルを使用することはできません **`switch`** 。

## <a name="stack-unwinding-example"></a>スタックアンワインドの例

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
