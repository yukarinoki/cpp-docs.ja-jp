---
title: 配列 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe8e5f53d05ac159fd577b260268f297b59d146
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="arrays-c"></a>配列 (C++)
配列は同様なオブジェクトのコレクションです。 配列の最も簡単な例は、次のシーケンスで宣言できるベクターです。  
  
```  
  
      decl-specifier identifier [ constant-expression ]  
decl-specifier identifier []  
decl-specifier identifer [][ constant-expression] . . .  
decl-specifier identifier [ constant-expression ]  
[ constant-expression ] . . .  
```  
  
 1. 宣言指定子:   
  
-   ストレージ クラスの指定子 (省略可能)。  
  
-   省略可能な**const**や`volatile`指定子。  
  
-   配列要素の型の名前。  
  
 2. 宣言子:   
  
-   識別子。  
  
-   角かっこで囲んだ整数型の定数式**です。** 追加の角かっこを使用して複数のディメンションが宣言されている場合は、角かっこの最初のセットに定数式を省略可能です。  
  
-   定数式を囲む追加の山かっこ (省略可能)。  
  
 3. 初期化子 (省略可能)。  参照してください[初期化子](../cpp/initializers.md)です。  
  
 配列の要素の数は、定数式によって取得できます。 配列の最初の要素は、ゼロ番目の要素と、最後の要素は、(*n*-1) 要素、場所*n*配列が格納できる要素の数です。 *定数式*整数型でなければなりませんし、0 より大きくなければなりません。 サイズが 0 の配列は配列の最後のフィールドが場合にのみ、`struct`または**共用体**Microsoft 拡張機能 (/Ze) が有効になっているとします。  
  
 次の例では、実行時に配列を定義する方法を示します。  
  
```  
// arrays.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main() {  
   using namespace std;  
   int size = 3, i = 0;  
  
   int* myarr = new int[size];  
  
   for (i = 0 ; i < size ; i++)  
      myarr[i] = 10;  
  
   for (i = 0 ; i < size ; i++)  
      printf_s("myarr[%d] = %d\n", i, myarr[i]);  
  
   delete [] myarr;  
}  
```  
  
 配列は派生型であるため、関数、参照、および `void` を除く他の派生型または基本型から生成できます。  
  
 他の配列から生成された配列は、多次元配列です。 これらの多次元配列は、角かっこで囲まれた定数式を複数並べることで指定されます。 たとえば、次の宣言について考えます。  
  
```  
int i2[5][7];  
```  
  
 これは、5 行 7 列の 2 次元行列に概念的に並べられる `int` 型の配列を指定します。  
  
 ![複数の概念レイアウト&#45;次元配列](../cpp/media/vc38rc1.gif "vc38RC1")  
多次元配列の概念レイアウト  
  
 初期化子リストを持つ多次元配列の宣言で (」の説明に従って[初期化子](../cpp/initializers.md))、最初の次元の境界を指定する定数式を省略することができます。 例えば:  
  
```  
// arrays2.cpp  
// compile with: /c  
const int cMarkets = 4;  
// Declare a float that represents the transportation costs.  
double TransportCosts[][cMarkets] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }  
};  
```  
  
 前の宣言は、3 行 x 4 列の配列を定義します。 行はファクトリを表し、列はファクトリの出荷先のマーケットを表します。 値は、ファクトリからマーケットへの輸送コストです。 配列の最初の次元は省かれますが、コンパイラは初期化子を調べることによってこれを入力します。  
  
 このセクションのトピック  
  
-   [配列の使用](../cpp/using-arrays-cpp.md)  
  
-   [式の配列](../cpp/arrays-in-expressions.md)  
  
-   [添字演算子の解釈](../cpp/interpretation-of-subscript-operator.md)  
  
-   [配列型の間接参照](../cpp/indirection-on-array-types.md)  
  
-   [C++ 配列の順序](../cpp/ordering-of-cpp-arrays.md)  
  
## <a name="example"></a>例  
 多次元配列の最初の次元の境界指定を省略する手法は、次のとおり関数宣言で使用することもできます。  
  
```  
// multidimensional_arrays.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <limits>   // Includes DBL_MAX  
#include <iostream>  
  
const int cMkts = 4, cFacts = 2;  
  
// Declare a float that represents the transportation costs  
double TransportCosts[][cMkts] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }    
};  
  
// Calculate size of unspecified dimension  
const int cFactories = sizeof TransportCosts /  
                  sizeof( double[cMkts] );  
  
double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);  
  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   double MinCost;  
  
   if (argv[1] == 0) {  
      cout << "You must specify the number of markets." << endl;  
      exit(0);  
   }  
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);  
   cout << "The minimum cost to Market " << argv[1] << " is: "  
       << MinCost << "\n";  
}  
  
double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {  
   double MinCost = DBL_MAX;  
  
   for( int i = 0; i < cFacts; ++i )  
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?  
         MinCost : TransportCosts[i][Mkt];  
  
   return MinCost;  
}  
```  
  
```Output  
The minimum cost to Market 3 is: 17.29  
```  
  
## <a name="comments"></a>コメント  
 `FindMinToMkt` 関数は、新しいファクトリを追加してもコード変更の必要はなく、再コンパイルだけすればいいように書かれています。  
  
## <a name="see-also"></a>関連項目  
 