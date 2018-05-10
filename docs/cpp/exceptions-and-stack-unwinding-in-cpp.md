---
title: 例外と C++ ではスタックがアンワインド |Microsoft ドキュメント
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
ms.openlocfilehash: b05b2f6240876540cd9e67d83bcb88242b68827b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++ での例外とスタック アンワインド
C++ 例外の機能では、制御は throw ステートメントから、スローされる型を処理できる最初の catch ステートメントに移動します。 呼ばれるプロセスで破棄はのすべての自動変数、throw 間のスコープ内および catch ステートメントを catch ステートメントに達すると、*スタック アンワインド*です。 スタック アンワインドでは、次のように実行されます。  
  
1.  通常の順次実行によって制御が `try` ステートメントに到達します。 `try` ブロック内の保護されたセクションが実行されます。  
  
2.  保護されたセクションの実行中に例外がスローされない場合、`catch` ブロックに続く `try` 句は実行されません。 実行は、関連付けられた `catch` ブロックに続く最後の `try` 句の後のステートメントに移って続行されます。  
  
3.  保護されたセクションの実行中または保護されたセクションで直接または間接的に呼び出される任意のルーチンで例外がスローされると、例外オブジェクトは `throw` オペランドで作成されたオブジェクトから作成されます  (これは、コピー コンストラクターが含まれる場合があることを意味します)。この時点で、コンパイラはスローされた例外の型を処理できるより高い実行コンテキストの `catch` 句、またはすべての型の例外を処理できる `catch` ハンドラーを検索します。 `catch` ハンドラーは、`try` ブロックの後で、記述した順序でチェックされます。 適切なハンドラーが見つからない場合、次の動的に囲まれている `try` ブロックが調べられます。 このプロセスは、最も外側を囲んでいる `try` ブロックがチェックされるまで続行されます。  
  
4.  一致するハンドラーが見つからない場合、またはアンワインド処理中に例外が発生した場合でも、ハンドラーが制御を取得する前であれば、定義済みのランタイム関数 `terminate` が呼び出されます。 例外がスローされた後でも、アンワインドが開始される前に例外が発生した場合は、`terminate` が呼び出されます。  
  
5.  一致している `catch` ハンドラーが見つかり、そのハンドラーが値でキャッチする場合、その仮パラメーターは例外オブジェクトをコピーして初期化されます。 参照によってキャッチする場合、例外オブジェクトを示すためにパラメーターが初期化されます。 正式なパラメーターが初期化されると、スタックをアンワインドするプロセスが開始されます。 これには、`try` ハンドラーに関連付けられた `catch` ブロックの開始から例外のスロー サイトまでの間に完全に構築された (まだ破棄されていない) すべての自動オブジェクトの破棄が含まれます。 破棄は、構築の逆順に発生します。 `catch` ハンドラーが実行され、最後のハンドラー (つまり、`catch` ハンドラーではない最初のステートメントまたは構造体) の後で、プログラムが実行を再開します。 `catch` ハンドラーに制御を入れることができるのはスローされた例外による場合だけで、`goto` ステートメント、または `case` ステートメントの `switch` ラベルによって入れることはできません。  
  
## <a name="stack-unwinding-example"></a>スタック アンワインドの例  
 次の例では、例外がスローされたときにスタックをアンワインドする方法を示します。 スレッド上で実行すると、`C` の throw ステートメントから `main` の catch ステートメントにジャンプし、その途中の各関数をアンワインドします。 `Dummy` オブジェクトが作成され、スコープ外として破棄される順序に注意してください。 関数が catch ステートメントを含む `main` なしで完了しないことにも注意してください。 関数 `A` はその `B()` の呼び出しから戻りません。`B` はその `C()` の呼び出しから戻りません。 `Dummy` ポインターの定義と対応する DELETE ステートメントをコメントから外してプログラムを実行すると、ポインターは削除されなくなります。 これは、関数が例外の保証を提供しない場合に発生することがある問題を示しています。 詳細については、「方法: 例外に対してデザインする」を参照してください。 catch ステートメントをコメント アウトすると、未処理の例外によってプログラムが終了するときの動作が示されます。  
  
```  
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