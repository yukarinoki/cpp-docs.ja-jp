---
title: インライン関数 (C++)
ms.date: 10/09/2018
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
- __inline
- _inline
- __forceinline
- _forceinline
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
ms.openlocfilehash: 703c04873a733d068da025b595909ecc681ff147
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374086"
---
# <a name="inline-functions-c"></a>インライン関数 (C++)

クラス宣言の本体で定義される関数はインライン関数です。

## <a name="example"></a>例

次のクラス宣言では、`Account` コンストラクターがインライン関数です。 メンバー関数`GetBalance`、 `Deposit`、`Withdraw`および は**インライン**として指定されていませんが、インライン関数として実装できます。

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
> クラス宣言では、関数は**inline**キーワードなしで宣言されました。 **inline**キーワードはクラス宣言で指定できます。結果は同じです。

特定のインライン メンバー関数は、すべてのコンパイル単位で同じ方法で宣言する必要があります。 この制約により、インライン関数は、インスタンス化された関数のように動作します。 また、インライン関数の定義は正確に 1 つだけあることが必要です。

クラス メンバー関数は、その関数の定義にインライン指定子が含まれている場合を除き、既定**で**外部リンケージに設定されます。 前の例は、これらの関数を**inline**指定子で明示的に宣言する必要はありません。関数定義**でインライン**を使用すると、インライン関数になります。 ただし、関数を呼び出した後**に関数をインライン**として宣言し直す方法は無効です。

## <a name="inline-__inline-and-__forceinline"></a>インライン、__inline、_forceinline \_

**インライン**および **__inline**指定子は、関数本体のコピーを関数が呼び出される各場所に挿入するようにコンパイラに指示します。

挿入 (インライン展開またはインライニングと呼ばれます) は、コンパイラの費用対効果分析により利益があるとわかった場合のみ発生します。 インライン展開では、関数呼び出しのオーバーヘッドが軽減されますが、コード サイズが大きくなるという潜在的なコストがあります。

**__forceinline**キーワードは、コスト/利益分析をオーバーライドし、代わりにプログラマの判断に依存します。 **__forceinline**を使用する場合は注意してください。 **__forceinline**を無差別に使用すると、パフォーマンスがわずかに向上するだけのコードが大きくなり、場合によってはパフォーマンスが低下する場合もあります (たとえば、より大きな実行可能ファイルのページングが増加するため)。

インライン関数を使用すると、関数呼び出しに関連するオーバーヘッドが回避されるため、プログラムを高速化できます。 インライン展開される関数は、標準の関数では使用できない、コードの最適化の対象になります。

インライン展開に関するオプションとキーワードは、インライン展開の対象となる候補をコンパイラに示すだけです。 関数がインライン展開される保証はありません。 **__forceinline**キーワードを指定しても、コンパイラで特定の関数をインライン化することはできません。 **/clr**を指定してコンパイルする場合、関数にセキュリティ属性が適用されている場合、コンパイラは関数をインライン化しません。

**インライン**キーワードは C++ でのみ使用できます。 **__inline**キーワードと **__forceinline**キーワードは、C および C++ の両方で使用できます。 以前のバージョンとの互換性のために **、_inline**と **_forceinline**は **__inline**の同義語であり、コンパイラ オプション[\(/Za 無効言語拡張) が](../build/reference/za-ze-disable-language-extensions.md)指定されていない限り **__forceinline。**

**インライン**キーワードは、インライン展開が優先されることをコンパイラに指示します。 ただし、コンパイラは、コードをインラインで挿入する代わりに、関数の別のインスタンスを作成 (インスタンス化) し、標準の呼び出しリンケージを作成できます。 このようになるのは、次の 2 つの場合です。

- 再帰関数。

- 翻訳単位の別の場所にあるポインターを通じて参照される関数。

これらの理由は、コンパイラの裁量でインライン展開を妨げる*可能性があります*。関数を**インライン化する場合**は、インライン指定子に依存しないでください。

通常の関数の場合と同様に、インライン関数への引数の評価の順序は定義されていません。 実際には、通常の関数呼び出しプロトコルで渡される引数の評価順序とは異なる場合があります。

[/Ob](../build/reference/ob-inline-function-expansion.md)コンパイラ最適化オプションは、インライン関数の展開が実際に発生するかどうかを判断するのに役立ちます。

[/LTCG](../build/reference/ltcg-link-time-code-generation.md)は、ソース コードで要求されたかどうかに関係なく、モジュール間のインライン展開を実行します。

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

クラスのメンバー関数は、**インライン**キーワードを使用するか、クラス定義内に関数定義を配置することによってインラインで宣言できます。

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

**マイクロソフト固有**

**__inline**キーワードは**インライン**と同じです。

**__forceinline**でも、コンパイラは、すべての状況でコードをインライン変換できません。 次の場合、コンパイラは関数をインライン展開できません。

- 関数またはその呼び出し元が /Ob0 (デバッグ ビルドの既定オプション) でコンパイルされる。

- 関数と呼び出し元が、異なる種類の例外処理を使用する (一方は C++ 例外処理、他方は構造化例外処理)。

- 関数に可変個引数リストが含まれている。

- 関数が /Og、/Ox、/O1、または /O2 を指定してコンパイルされていない場合に、インライン アセンブリを使用する。

- 関数は再帰的であり **、#pragmainline_recursion(on)を**伴いません。 プラグマによって、再帰関数はインライン展開され、既定の深さは 16 呼び出しになります。 インラインの深さを減らすには、プラグマ[inline_depth](../preprocessor/inline-depth.md)使用します。

- 関数が仮想で、仮想的に呼び出される。 仮想関数への直接呼び出しはインライン展開できます。

- プログラムが関数のアドレスを受け取り、関数へのポインターによって呼び出される。 受け取られるアドレスを持っている関数への直接呼び出しはインライン展開できます。

- また、この関数には[、裸](../cpp/naked-cpp.md)の[__declspec](../cpp/declspec.md)修飾子も付けられます。

コンパイラが **__forceinline**で宣言された関数をインライン化できない場合、次の場合を除いてレベル 1 の警告が生成されます。

- この関数は、/Od または /Ob0 を使用してコンパイルされます。 このような場合は、インライン化は期待されていません。

- 関数は、外部、組み込まれたライブラリまたは別の翻訳単位で定義されているか、仮想呼び出しターゲットまたは間接呼び出しターゲットです。 コンパイラは、現在の翻訳単位で見つけられないインラインコードを識別できません。

再帰関数は[、inline_depth](../preprocessor/inline-depth.md)プラグマで指定された深さにインラインで置き換えることができます ( 最大 16 呼び出しまで) 。 その深さの後、再帰関数の呼び出しは、関数のインスタンスへの呼び出しとして扱われます。  再帰関数がインライン ヒューリスティックによってチェックされる深さは、16 を超えることはできません。 [inline_recursion](../preprocessor/inline-recursion.md)プラグマは、現在拡張中の関数のインライン展開を制御します。 関連情報については、[インライン関数拡張](../build/reference/ob-inline-function-expansion.md)(/Ob) コンパイラー・オプションを参照してください。

**エンド マイクロソフト 固有**

**インライン**指定子の使用の詳細については、以下を参照してください。

- [インライン クラス メンバー関数](../cpp/inline-functions-cpp.md)

- [dllexport と dllimport を使用したインライン C++ 関数の定義](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>インライン関数を使用する状況

インライン関数は、プライベート データ メンバーにアクセスする関数のような小さな関数に使用するのが最適です。 これらの 1 行または 2 行の "アクセサー" 関数の主な目的は、オブジェクトに関する状態情報を返すことです。短い関数は、関数呼び出しのオーバーヘッドに敏感です。 長い関数は、呼び出すシーケンスと返すシーケンスにかかる時間が相対的に少なく、インライン展開の利点が少なくなります。

クラス`Point`は次のように定義できます。

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

座標操作は、このようなクラスのクライアントでは比較的一般的な操作であると仮定すると **、2**つのアクセサー`x`関数`y`(および前の例では) をインラインとして指定すると、通常はオーバーヘッドが節約されます。

- 関数呼び出し (パラメーターの引き渡しおよびスタックへのオブジェクトのアドレスの配置を含む)

- 呼び出し元のスタック フレームの保持

- 新しいスタック フレームのセットアップ

- 戻り値のやり取り

- 元のスタック フレームの復元

- 戻り値

## <a name="inline-functions-vs-macros"></a>インライン関数とマクロ

インライン関数はマクロに似ていますが、インライン関数がコンパイラによって解析されるのに対し (関数コードはコンパイル時に呼び出しの時点で展開されるため)、マクロはプリプロセッサによって展開されます。 そのため、これらにはいくつかの重要な違いがあります。

- インライン関数は、通常の関数に適用されるタイプ セーフのすべてのプロトコルに従います。

- インライン関数は、関数宣言に**inline**キーワードを含める点を除いて、他の関数と同じ構文を使用して指定します。

- インライン関数に引数として渡された式は、1 回だけ評価されます。 マクロでは、引数として渡された式が複数回評価される可能性があります。

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

式`toupper(getc(stdin))`の目的は、文字をコンソール・デバイス ( )`stdin`から読み取り、必要に応じて大文字に変換する必要があることです。

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

[noinline](../cpp/noinline.md)<br/>
[auto_inline](../preprocessor/auto-inline.md)
