---
title: 型変換とタイプ セーフ (Modern C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13dabba7b7cfc769d91471c2dfc6f92f1b414996
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32424777"
---
# <a name="type-conversions-and-type-safety-modern-c"></a>型変換とタイプ セーフ (Modern C++)
このドキュメントでは、共通型の変換に伴う問題を識別し、C++ コードでそれらを回避する方法を説明します。  
  
 C ++.のプログラムを作成するときは、そのプログラムがタイプ セーフであることを確認することが重要です。 これは、すべての変数、関数の引数、および関数の戻り値が適切な種類のデータを格納すること、異なる型の値が関係する操作が "意味のある" 処理を行うこと、さらにデータ損失、ビット パターンの誤った解釈、メモリ破損を発生させないことを意味します。 プログラムが、明示的または暗黙的に、ある型の値を他の型に変換しないことが、定義上のタイプ セーフです。 ただし、型の変換、また場合によっては安全でない変換が必須になることもあります。 たとえば、`int` 型の変数に浮動小数点演算の結果を格納する必要が生じることや、unsigned `int` に値を格納して、signed `int` を受け取る関数に渡す必要が生じることもあります。 どちらの例も、データ損失や値の再解釈を引き起こす可能性があるため、安全ではない変換を示していると言えます。  
  
 コンパイラが安全ではない変換を検出した場合は、エラーまたは警告を発行します。 エラーが生じた場合はコンパイルが中止されます。警告が生じた場合は、コンパイルは続行されますが、コード内にエラーが存在する可能性が示されます。 ただし、警告なしでプログラムがコンパイルされた場合でも、正しくない結果を生成する暗黙の型変換につながるコードが存在している可能性があります。 型エラーは、コード内の明示的な変換、またはキャストによって発生する可能性があります。  
  
## <a name="implicit-type-conversions"></a>暗黙的な型変換  
 コンパイラが組み込みを使用して、式には、異なる組み込み型のオペランドが含まれているし、明示的なキャストが存在しない、*標準変換*型が一致するように、オペランドの 1 つを変換します。 コンパイラはいずれかが成功するまで、適切に定義された一連の変換を試みます。 選択した変換が上位変換である場合は、コンパイラは警告を発行しません。 変換が縮小変換である場合は、コンパイラは、データ損失の可能性に関する警告を発行します。 実際のデータ損失が発生するかどうかは、関与する実際の値に依存しますが、この警告をエラーとして扱うことをお勧めします。 ユーザー定義型が関与している場合は、コンパイラは、ユーザーがクラス定義の中で指定した変換を使用しようとします。 受け入れ可能な変換が見つからない場合は、コンパイラはエラーを発行し、プログラムをコンパイルしません。 標準の変換を制御するルールの詳細については、次を参照してください。[標準変換](../cpp/standard-conversions.md)です。 ユーザー定義の変換の詳細については、次を参照してください。[ユーザー定義の変換 (C + + CLI)](../dotnet/user-defined-conversions-cpp-cli.md)です。  
  
### <a name="widening-conversions-promotion"></a>拡大変換 (上位変換)  
 拡大変換では、より小さい変数内の値が、より大きい変数に代入され、データは失われません。 拡大変換は常に安全であるため、コンパイラはこの変換を自動的に実行し、警告を発行しません。 次の変換は、拡大変換です。  
  
|From|終了|  
|----------|--------|  
|`long long` または `__int64` を除く、他のすべての符号付きまたは符号なし整数型|`double`|  
|`bool` または `char`|他のすべての組み込み型|  
|`short` または `wchar_t`|`int`、`long`、`long long`|  
|`int`, `long`|`long long`|  
|`float`|`double`|  
  
### <a name="narrowing-conversions-coercion"></a>縮小変換 (強制型)  
 コンパイラは、暗黙的に縮小変換を実行しますが、データ損失の可能性に関する警告を発行します。 これらの警告を重大なものとして受け止めてください。 大きい変数の中にある値が、小さい変数の中に必ず収容でき、データ損失が発生しないことが確実な場合は、コンパイラが今後警告を発行しないように、明示的なキャストを追加してください。 変換が安全かどうか自信がない場合は、コード内になんらかの種類の実行時チェックを追加し、発生する可能性のあるデータ損失に対処できるようにしてください。その結果、プログラムが誤った結果を生成することはありません。 
  
 浮動小数点型から整数型へのあらゆる変換は、浮動小数点値の小数部が破棄されて失われるため、縮小変換です。  
  
 次のコード例では、いくつかの暗黙的な縮小変換と、それらに関してコンパイラが発行する警告を示します。  
  
```cpp  
int i = INT_MAX + 1; //warning C4307:'+':integral constant overflow  
wchar_t wch = 'A'; //OK  
char c = wch; // warning C4244:'initializing':conversion from 'wchar_t'  
              // to 'char', possible loss of data  
unsigned char c2 = 0xfffe; //warning C4305:'initializing':truncation from  
                           // 'int' to 'unsigned char'  
int j = 1.9f; // warning C4244:'initializing':conversion from 'float' to  
              // 'int', possible loss of data  
int k = 7.7; // warning C4244:'initializing':conversion from 'double' to  
             // 'int', possible loss of data  
```  
  
### <a name="signed---unsigned-conversions"></a>符号付き - 符号なしの変換  
 符号付き整数型と符号なし整数型は常に同じサイズですが、値変換の目的でビット パターンを解釈する方法が異なります。 次のコード例は、同じビット パターンが符号付きの値、および符号なしの値として解釈されるときの動作を示します。 `num` と `num2` の両方に格納されているビット パターンは、前の図から決して変化していません。  
  
```cpp  
using namespace std;  
unsigned short num = numeric_limits<unsigned short>::max(); // #include <limits>  
short num2 = num;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
// Go the other way.  
num2 = -1;  
num = num2;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
```  
  
 値の再解釈が双方向で発生することに注意してください。 期待される値に対して、符号が反転したように思える奇妙な結果をプログラムが返した場合は、符号付き整数型と符号なし整数型の間で暗黙的な変換が実行された可能性に注目してください。 次の例では、式の結果 (0 - 1) から暗黙的に変換が`int`に`unsigned int`に格納されているときに`num`です。 この結果、ビット パターンの再解釈が発生します。  
  
```cpp  
unsigned int u3 = 0 - 1;  
cout << u3 << endl; // prints 4294967295  
  
```  
  
 符号付きと符号なし整数型の間の暗黙的な変換について、コンパイラは警告を発行しません。 したがって、符号付きから符号なしへの変換を決して実施しないことをお勧めします。 このような変換を回避できない場合は、変換されようとしている値が 0 以上であるかどうか、および符号付きの型の最大値以下であるかどうかを検出する実行時チェックをコードに追加してください。 この範囲内にある値は、再解釈なしで、符号付きから符号なし、および符号なしから符号付きへと変換されます。  
  
### <a name="pointer-conversions"></a>ポインター変換  
 多くの式では、C 形式の配列は、配列内の最初の要素へのポインターに暗黙的に変換され、また定数変換が警告なしで実施される可能性があります。 これは便利ですが、場合によってはエラーが発生しやすくなります。 たとえば、不適切に設計され次のコード例は、無意味のように見えますが、Visual C++ 内でコンパイルされ、'p' という結果を生成します。 まず、"Help" 文字列定数リテラルは `char*` に変換されます。このポインターは 配列の最初の要素を指し、3 つの要素によってインクリメントされます。その結果、最後の要素 'p' を指すようになります。  
  
```cpp  
char* s = "Help" + 3;  
  
```  
  
## <a name="explicit-conversions-casts"></a>明示的な変換 (キャスト)  
 キャスト操作を使用すると、ある型の値を別の型に変換するようにコンパイラに指示できます。 2 つの方が完全に無関係である場合はコンパイラはエラーを生成しますが、操作がタイプ セーフでない場合でもエラーを生成しない状況が存在します。 キャストは控えめに使用してください。ある型から別の型への変換は、プログラム エラーの原因となる可能性があるためです。 ただし、時にはキャストが必須であり、すべてのキャストが等しく危険というわけでもありません。 キャストの 1 つの効率的な使用方法は、コードが縮小変換を実行し、その変換により、プログラムが不適切な結果をもたらさないことがわかっている場合です。 実際には、何を実行するかを開発者が理解していて、その点に関する警告を発行しないようにコンパイラに指示することになります。 別の使用法は、ポインターから派生クラス、およびポインターから基底クラスへのキャストです。 別の使用法は、変数の `const` (定数) 特性を放棄し、その変数を、`const` 以外の引数を必要とする関数に渡すことです。 これらのキャスト操作のほとんどには、ある程度のリスクが存在します。  
  
 C スタイルのプログラミングでは、同じ C スタイルのキャスト演算子が、あらゆる種類のキャストに使用されます。  
  
```cpp  
(int) x; // old-style cast, old-style syntax  
int(x); // old-style cast, functional syntax  
  
```  
  
 つまり、C スタイルのキャスト演算子は、呼び出し演算子 () と同じものであり、したがって、コードの中で目立たず、簡単に見過ごす可能性があります。 眺めたときに認識するのが困難で、検索も困難であるため、どちらも望ましくない特性です。また、`static`、`const`、および `reinterpret_cast` の組み合わせを呼び出すには、非常に多くの形態を使用することになります。 古いスタイルのキャストの実際の動作を理解するのは困難で、エラーが発生しやすくなります。 これらすべての理由により、キャストがどうしても必要な場合は、次の C++ スタイルのキャスト操作のいずれかを使用することをお勧めします。特定の状況では、かなりタイプ セーフであり、プログラミングの意図を非常に明確に表現できるからです。  
  
-   `static_cast` は、コンパイル時にのみチェックされるキャストに対応します。 `static_cast` を指定すると、完全に互換性のない型の間でキャストを行おうとしていることをコンパイラが検出した場合に、エラーが返されます。 これを、基本型へのポインターと、派生形へのポインターの間でのキャストに使用することもできますが、コンパイラはこのような変換が実行時に安全かどうかを必ず判定できるわけではありません。  
  
    ```cpp  
    double d = 1.58947;  
    int i = d;  // warning C4244 possible loss of data  
    int j = static_cast<int>(d);       // No warning.  
    string s = static_cast<string>(d); // Error C2440:cannot convert from  
                                       // double to std:string  
  
    // No error but not necessarily safe.  
    Base* b = new Base();  
    Derived* d2 = static_cast<Derived*>(b);  
  
    ```  
  
     詳細については、次を参照してください。 [static_cast](../cpp/static-cast-operator.md)です。  
  
-   `dynamic_cast`は、基本型へのポインターから、派生形のポインターへのキャストに関する、安全な実行時チェックに対応します。 ダウンキャストの場合、`dynamic_cast` は、`static_cast` より安全ですが、実行時チェックにはある程度のオーバーヘッドがあります。  
  
    ```cpp  
    Base* b = new Base();  
  
    // Run-time check to determine whether b is actually a Derived*  
    Derived* d3 = dynamic_cast<Derived*>(b);  
  
    // If b was originally a Derived*, then d3 is a valid pointer.  
    if(d3)  
    {  
       // Safe to call Derived method.  
       cout << d3->DoSomethingMore() << endl;  
    }  
    else  
    {  
       // Run-time check failed.  
       cout << "d3 is null" << endl;  
    }  
  
    //Output: d3 is null;  
  
    ```  
  
     詳細については、次を参照してください。 [dynamic_cast](../cpp/dynamic-cast-operator.md)です。  
  
-   `const_cast` は、変数の `const` (定数) 特性を放棄する場合や、`const` (定数) ではない変数を `const` (定数) に変換する場合に対応します。 この演算子を使用して `const` (定数) 特性を放棄する方法は、C スタイルのキャストと同様、エラーが発生しやすくなります。ただし、`const-cast` を使用する場合は、誤ってキャストを実行する可能性は低くなります。 時には、変数の `const` (定数) 特性を放棄する必要が生じることがあります。たとえば、`const` (定数) 変数を、`const` (定数) 以外のパラメーターを受け取る関数に渡す場合です。 その方法を次の例に示します。  
  
    ```cpp  
    void Func(double& d) { ... }  
    void ConstCast()  
    {  
       const double pi = 3.14;  
       Func(const_cast<double&>(pi)); //No error.  
    }  
  
    ```  
  
     詳細については、次を参照してください。 [const_cast](../cpp/const-cast-operator.md)です。  
  
-   `reinterpret_cast` は、`pointer` から `int` へのキャストなど、関連のない型の間でのキャストに対応します。  
  
    > [!NOTE]
    >  このキャスト演算子は、他のキャスト演算子ほどの頻度では使用されず、他のコンパイラへの移植性も保証されません。  
  
     次の例では、`reinterpret_cast` が `static_cast` とはどのように異なっているかを示します。  
  
    ```cpp  
    const char* str = "hello";  
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot  
                                  // convert from 'const char *' to 'int'  
    int j = (int)str; // C-style cast. Did the programmer really intend  
                      // to do this?  
    int k = reinterpret_cast<int>(str);// Programming intent is clear.  
                                       // However, it is not 64-bit safe.  
  
    ```  
  
     詳細については、次を参照してください。 [reinterpret_cast Operator](../cpp/reinterpret-cast-operator.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ 型システム](../cpp/cpp-type-system-modern-cpp.md)   
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)