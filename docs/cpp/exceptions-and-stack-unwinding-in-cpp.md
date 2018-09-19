---
title: 例外と C++ のスタックがアンワインド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a413179ca2c44d1a66ae1702c690039383d1045
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032212"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++ での例外とスタック アンワインド

C++ 例外の機能では、制御は throw ステートメントから、スローされる型を処理できる最初の catch ステートメントに移動します。 Catch ステートメントに達すると、すべてスローの間のスコープ内にあるし、catch ステートメントを自動変数の破棄と呼ばれるプロセスで*スタック アンワインド*します。 スタック アンワインドでは、次のように実行されます。

1. コントロールに達すると、**お試しください**通常の順次実行によってステートメント。 保護されたセクションで、**お試しください**ブロックが実行されます。

1. 保護されたセクションの実行中に例外がスローされない場合、**キャッチ**に従って句、**お試しください**ブロックは実行されません。 実行は、最後の後のステートメントで続行**キャッチ**句を関連付けられている**お試しください**ブロック。

1. によって作成されるオブジェクトから例外オブジェクトを作成または保護されたセクションが直接的または間接的に呼び出す任意のルーチンで保護されたセクションの実行中に例外がスローされた場合、**スロー**オペランド。 (これは、コピー コンストラクターが含まれる場合があることを意味します)。コンパイラがこの時点では、検索、**キャッチ**スローされる型の例外を処理できるより高い実行コンテキストの句、**キャッチ**任意の種類の例外を処理できるハンドラー。 **キャッチ**ハンドラーは、後で、記述の順序でチェックされます、**お試しください**ブロックします。 適切なハンドラーが見つからないかどうか、次に動的に囲んでいる**お試しください**ブロックが調べられます。 このプロセスは、最も外側を囲むまで継続**お試しください**ブロックが調べられます。

1. 一致するハンドラーが見つからない場合、またはアンワインド処理中に例外が発生した場合でも、ハンドラーが制御を取得する前であれば、定義済みのランタイム関数 `terminate` が呼び出されます。 例外がスローされた後でも、アンワインドが開始される前に例外が発生した場合は、`terminate` が呼び出されます。

1. 一致する場合**キャッチ**ハンドラーが見つかると、値によってキャッチして、その仮パラメーターは、例外オブジェクトをコピーして初期化されます。 参照によってキャッチする場合、例外オブジェクトを示すためにパラメーターが初期化されます。 正式なパラメーターが初期化されると、スタックをアンワインドするプロセスが開始されます。 これは、完全に構築されたすべての自動オブジェクトの破棄: まだ破棄されますが、-の先頭の間、**を再試行してください**ブロックに関連付けられている、**キャッチ**ハンドラーとサイトの例外をスローします。 破棄は、構築の逆順に発生します。 **キャッチ**ハンドラーが実行され、プログラムの最後のハンドラーの後の実行が再開-は、最初のステートメントまたはない構造体で、**キャッチ**ハンドラー。 コントロールが入力できるだけ、**キャッチ**でスローされた例外ハンドラーを影響はありません、 **goto**ステートメントまたは**ケース**でラベル付け、**スイッチ**ステートメント。

## <a name="stack-unwinding-example"></a>スタック アンワインドの例

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