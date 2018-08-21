---
title: インライン関数 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b39a6889dfd8a28d65aebcab04881d4bc28ce1e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403668"
---
# <a name="inline-functions-c"></a>インライン関数 (C++)
クラス宣言の本体で定義される関数はインライン関数です。  
  
## <a name="example"></a>例  
 次のクラス宣言では、`Account` コンストラクターがインライン関数です。 メンバー関数は、 `GetBalance`、 `Deposit`、および`Withdraw`として指定されていない**インライン**がインライン関数として実装することができます。  
  
```cpp 
// Inline_Member_Functions.cpp  
class Account  
{  
public:  
    Account(double initial_balance) { balance = initial_balance; }  
    double GetBalance();  
    double Deposit( double Amount );  
    double Withdraw( double Amount );  
private:  
    double balance;  
};  
  
inline double Account::GetBalance()  
{  
    return balance;  
}  
  
inline double Account::Deposit( double Amount )  
{  
    return ( balance += Amount );  
}  
  
inline double Account::Withdraw( double Amount )  
{  
    return ( balance -= Amount );  
}  
int main()  
{  
}  
```  
  
> [!NOTE]
>  せず、クラス宣言で宣言された関数、**インライン**キーワード。 **インライン**クラス宣言でキーワードを指定することができます。 結果は同じです。  
  
 特定のインライン メンバー関数は、すべてのコンパイル単位で同じ方法で宣言する必要があります。 この制約により、インライン関数は、インスタンス化された関数のように動作します。 また、インライン関数の定義は正確に 1 つだけあることが必要です。  
  
 その関数の定義が含まれていない場合、クラス メンバー関数の外部リンケージを既定値、**インライン**指定子。 前の例をこれらの関数必要がありますいない明示的に宣言すると、**インライン**指定子を使用して**インライン**関数の定義、インライン関数を使用すると、します。 ただし、関数として再宣言するされていない**インライン**その関数を呼び出した後。  
  
## <a name="inline-inline-and-forceinline"></a>Inline、_ _inline、および\__forceinline  
 **インライン**と **_ _inline**指定子、関数が呼び出される適切な各場所に、関数本体のコピーを挿入するようコンパイラに指示します。  
  
 挿入 (インライン展開またはインライニングと呼ばれます) は、コンパイラの費用対効果分析により利益があるとわかった場合のみ発生します。 インライン展開では、関数呼び出しのオーバーヘッドが軽減されますが、コード サイズが大きくなるという潜在的なコストがあります。  
  
 **_ _Forceinline**キーワードは、費用対効果分析をオーバーライドし、代わりにプログラマの判断に依存しています。 使用する場合は注意 **_ _forceinline**します。 区別しないで使用 **_ _forceinline**マージナル パフォーマンスの向上だけで大規模なコードが発生したり、場合によっては、(ページングが増えるためより大きな実行可能ファイルなど) のパフォーマンスの低下もします。  
  
 インライン関数を使用すると、関数呼び出しに関連するオーバーヘッドが回避されるため、プログラムを高速化できます。 インライン展開される関数は、標準の関数では使用できない、コードの最適化の対象になります。  
  
 インライン展開に関するオプションとキーワードは、インライン展開の対象となる候補をコンパイラに示すだけです。 関数がインライン展開される保証はありません。 使用しても、特定の関数のインライン展開を強制することはできません、 **_ _forceinline**キーワード。 コンパイルするときに **/clr**コンパイラはインラインではなく、関数、関数に適用されるセキュリティ属性がある場合。  
  
 **インライン**キーワードは C++ でのみ使用できます。 **_ _Inline**と **_ _forceinline**キーワードは C および C++ の両方で使用します。 以前のバージョンとの互換性のため **_inline**のシノニムです **_ _inline**します。  
  
 **インライン**キーワードは、インライン展開が優先されることをコンパイラに指示します。 ただし、コンパイラは、コードをインラインで挿入する代わりに、関数の別のインスタンスを作成 (インスタンス化) し、標準の呼び出しリンケージを作成できます。 このようになるのは、次の 2 つの場合です。  
  
-   再帰関数。  
  
-   翻訳単位の別の場所にあるポインターを通じて参照される関数。  
  
 これらの理由を妨げる可能性、インライン展開*may 他のユーザーと*、;、コンパイラの裁量でする必要がありますに依存しない、**インライン**のためインライン化できません関数指定子。  
  
 通常の関数の場合と同様に、インライン関数への引数の評価の順序は定義されていません。 実際には、通常の関数呼び出しプロトコルで渡される引数の評価順序とは異なる場合があります。  
  
 [/Ob](../build/reference/ob-inline-function-expansion.md)コンパイラ最適化オプションは、関数のインライン展開が実際に発生するかどうかを判断するのに役立ちます。  
  
 [/LTCG](../build/reference/ltcg-link-time-code-generation.md)クロス モジュール ソース コードで要求されたかどうかにかかわらずインライン化を実行します。  
  
### <a name="example-1"></a>例 1  
  
```cpp 
// inline_keyword1.cpp  
// compile with: /c  
inline int max( int a , int b ) {  
   if( a > b )   
      return a;  
   return b;  
}  
```  
  
 クラスのメンバー関数を使用してインラインで宣言することができます、**インライン**キーワードまたはクラス定義内で関数の定義を配置することで。  
  
### <a name="example-2"></a>例 2  
  
```cpp 
// inline_keyword2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
  
class MyClass {  
public:  
   void print() { cout << i << ' '; }   // Implicitly inline  
private:  
   int i;  
};  
```  
  
### <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 **_ _Inline**キーワードは等価**インライン**します。  
  
 使用しても **_ _forceinline**コンパイラは、すべての環境でのインライン コードをことはできません。 次の場合、コンパイラは関数をインライン展開できません。  
  
-   関数またはその呼び出し元が /Ob0 (デバッグ ビルドの既定オプション) でコンパイルされる。  
  
-   関数と呼び出し元が、異なる種類の例外処理を使用する (一方は C++ 例外処理、他方は構造化例外処理)。  
  
-   関数に可変個引数リストが含まれている。  
  
-   関数が /Og、/Ox、/O1、または /O2 を指定してコンパイルされていない場合に、インライン アセンブリを使用する。  
  
-   関数は再帰的なとが付属しない **#pragma inline_recursion**します。 プラグマによって、再帰関数はインライン展開され、既定の深さは 16 呼び出しになります。 インラインの深度を減らすためには、次のように使用します。 [inline_depth](../preprocessor/inline-depth.md)プラグマ。  
  
-   関数が仮想で、仮想的に呼び出される。 仮想関数への直接呼び出しはインライン展開できます。  
  
-   プログラムが関数のアドレスを受け取り、関数へのポインターによって呼び出される。 受け取られるアドレスを持っている関数への直接呼び出しはインライン展開できます。  
  
-   関数が付いたしても、 [naked](../cpp/naked-cpp.md) [_ _declspec](../cpp/declspec.md)修飾子。  
  
 場合、コンパイラはインラインで宣言された関数 **_ _forceinline**、場合を除き、レベル 1 の警告が生成されます。
  
-   /Od か、/Ob0 を使用して、関数がコンパイルされます。 いいえインライン展開が、このような場合に必要です。     
  
-   関数は、含まれるライブラリまたは別の翻訳単位の外部で定義されているまたはが仮想呼び出しのターゲットまたは間接的な呼び出しのターゲット。 コンパイラは、現在の翻訳単位内に見つからないことを示す非インライン コードを識別できません。  
  
 再帰関数はインラインで置き換えるによって指定される深度を指定できます、 [inline_depth](../preprocessor/inline-depth.md)プラグマを最大 16 の呼び出し。 その深さの後、再帰関数の呼び出しは、関数のインスタンスへの呼び出しとして扱われます。  再帰関数がインライン ヒューリスティックによってチェックされる深さは、16 を超えることはできません。 [Inline_recursion](../preprocessor/inline-recursion.md)プラグマは、現在展開中の関数のインライン展開を制御します。 参照してください、[関数のインライン展開](../build/reference/ob-inline-function-expansion.md)(/Ob) 関連情報については、コンパイラ オプション。  
  
**Microsoft 固有の仕様はここまで**  
 使用しての詳細については、**インライン**指定子を参照してください。  
  
-   [インライン クラス メンバー関数します。](../cpp/inline-functions-cpp.md)  
  
-   [dllexport と dllimport を使用したインライン C 関数の定義](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
## <a name="when-to-use-inline-functions"></a>インライン関数を使用する状況  
 インライン関数は、プライベート データ メンバーにアクセスする関数のような小さな関数に使用するのが最適です。 これらの 1 行または 2 行の "アクセサー" 関数の主な目的は、オブジェクトに関する状態情報を返すことです。短い関数は、関数呼び出しのオーバーヘッドに敏感です。 長い関数は、呼び出すシーケンスと返すシーケンスにかかる時間が相対的に少なく、インライン展開の利点が少なくなります。  
  
 A`Point`クラスは、次のように定義できます。  
  
```cpp 
// when_to_use_inline_functions.cpp  
class Point  
{  
public:  
    // Define "accessor" functions as  
    //  reference types.  
    unsigned& x();  
    unsigned& y();  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
inline unsigned& Point::x()  
{  
    return _x;  
}  
inline unsigned& Point::y()  
{  
    return _y;  
}  
int main()  
{  
}  
```  
  
 座標の操作がクライアントでこのようなクラスの 2 つのアクセサー関数を指定することは比較的一般的な操作を (`x`と`y`前の例) として**インライン**通常を保存します、上のオーバーヘッド。  
  
-   関数呼び出し (パラメーターの引き渡しおよびスタックへのオブジェクトのアドレスの配置を含む)  
  
-   呼び出し元のスタック フレームの保持  
  
-   新しいスタック フレームのセットアップ  
  
-   戻り値のやり取り  
  
-   元のスタック フレームの復元  
  
-   Return  
  
## <a name="inline-functions-vs-macros"></a>インライン関数とマクロの比較  
 インライン関数はマクロに似ていますが、インライン関数がコンパイラによって解析されるのに対し (関数コードはコンパイル時に呼び出しの時点で展開されるため)、マクロはプリプロセッサによって展開されます。 そのため、これらにはいくつかの重要な違いがあります。  
  
-   インライン関数は、通常の関数に適用されるタイプ セーフのすべてのプロトコルに従います。  
  
-   インライン関数を指定する点が異なりますとして他の関数と同じ構文を使用して、**インライン**関数の宣言でキーワード。  
  
-   インライン関数に引数として渡された式は、1 回だけ評価されます。 マクロでは、引数として渡された式が複数回評価される可能性があります。  
  
 次の例は、小文字を大文字に変換するマクロを示しています。  
  
```cpp 
// inline_functions_macro.c  
#include <stdio.h>  
#include <conio.h>  
  
#define toupper(a) ((a) >= 'a' && ((a) <= 'z') ? ((a)-('a'-'A')):(a))  
  
int main() {  
   char ch;  
   printf_s("Enter a character: ");  
   ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
//  Sample Input:  xyz  
// Sample Output:  Z  
```  
  
 式の目的は、`toupper(getc(stdin))`コンソール デバイスからの文字が読み取られるは (`stdin`) と、必要に応じてが大文字に変換します。  
  
 マクロの実装により、入力文字が "a" 以上であるかどうかを判断するため `getc` が 1 回実行され、さらにその文字が "z" 以下であるかどうかを判断するためもう 1 回実行されます。 入力文字がその範囲にある場合、`getc` が再実行されて、文字が大文字に変換されます。 つまり、このプログラムでは文字を 2 回または 3 回にわたって待機しますが、待機は 1 回だけに抑えるのが本来最適な方法です。  
  
 インライン関数を使用すると、このような問題が解消されます。  
  
```cpp 
// inline_functions_inline.cpp  
#include <stdio.h>  
#include <conio.h>  
  
inline char toupper( char a ) {  
   return ((a >= 'a' && a <= 'z') ? a-('a'-'A') : a );  
}  
  
int main() {  
   printf_s("Enter a character: ");  
   char ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
```  
  
```Output  
Sample Input: a  
Sample Output: A  
```  
  
## <a name="see-also"></a>関連項目  
 [noinline](../cpp/noinline.md)   
 [auto_inline](../preprocessor/auto-inline.md)