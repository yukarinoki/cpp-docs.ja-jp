---
title: インライン関数 (C++)
description: C++ inline キーワードを使用すると、コンパイラにインライン関数を提案できます。
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
ms.openlocfilehash: d2356d7813167f3973ac2748423c6af7f0b5573b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227414"
---
# <a name="inline-functions-c"></a>インライン関数 (C++)

クラス宣言の本体で定義される関数はインライン関数です。

## <a name="example"></a>例

次のクラス宣言では、`Account` コンストラクターがインライン関数です。 メンバー関数 `GetBalance` 、 `Deposit` 、およびは、とし `Withdraw` て指定されていません **`inline`** が、インライン関数として実装できます。

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
> クラス宣言では、キーワードを使用せずに関数が宣言されました **`inline`** 。 キーワードは、 **`inline`** クラス宣言で指定できます。結果は同じです。

特定のインライン メンバー関数は、すべてのコンパイル単位で同じ方法で宣言する必要があります。 この制約により、インライン関数は、インスタンス化された関数のように動作します。 また、インライン関数の定義は正確に 1 つだけあることが必要です。

クラスメンバー関数は、その関数の定義に指定子が含まれていない限り、既定で外部リンケージに設定され **`inline`** ます。 前の例では、指定子を使用してこれらの関数を明示的に宣言する必要がないことを示してい **`inline`** ます。 **`inline`** 関数定義でを使用すると、インライン関数になります。 ただし、 **`inline`** その関数を呼び出した後に関数を再宣言することはできません。

## <a name="inline-__inline-and-__forceinline"></a>`inline`、`__inline`、`__forceinline`

**`inline`** および指定子は、関数 **`__inline`** が呼び出される各場所に関数本体のコピーを挿入するようコンパイラに指示します。

*インライン展開*またはインライン*展開*と呼ばれる挿入は、コンパイラのコスト便益分析によって価値があることが示されている場合にのみ発生します。 インライン展開では、コードサイズが大きくなる可能性があるため、関数呼び出しのオーバーヘッドが最小限に抑えられます。

**`__forceinline`** キーワードはコスト効果分析をオーバーライドし、代わりにプログラマの判断に依存します。 を使用する場合は注意が必要 **`__forceinline`** です。 区別を使用する **`__forceinline`** と、パフォーマンスがわずかに向上するだけでなく、場合によってはパフォーマンスが低下する可能性があります (たとえば、大規模な実行可能ファイルのページングが増加しているため)。

インライン関数を使用すると、関数呼び出しに関連するオーバーヘッドが回避されるため、プログラムを高速化できます。 インライン展開される関数は、標準の関数では使用できない、コードの最適化の対象になります。

インライン展開に関するオプションとキーワードは、インライン展開の対象となる候補をコンパイラに示すだけです。 関数がインライン化される保証はありません。 キーワードを使用しても、特定の関数を強制的にインライン化することはできません **`__forceinline`** 。 を使用してコンパイルする場合、 **`/clr`** 関数にセキュリティ属性が適用されていると、コンパイラは関数をインライン化しません。

**`inline`** キーワードは、C++ でのみ使用できます。 **`__inline`** キーワードと **`__forceinline`** キーワードは、C と C++ の両方で使用できます。 以前のバージョンとの互換性のため、 **`_inline`** と **`_forceinline`** はのシノニムであり、 **`__inline`** コンパイラオプションの [ **`__forceinline`** [ `/Za` \( 言語拡張機能を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されている場合を除きます。

キーワードは、 **`inline`** インライン展開が優先されることをコンパイラに指示します。 ただし、コンパイラは、コードをインラインで挿入する代わりに、関数の別のインスタンスを作成 (インスタンス化) し、標準の呼び出しリンケージを作成できます。 この動作が発生する可能性がある2つのケースを次に示します。

- 再帰関数。

- 翻訳単位の別の場所にあるポインターを通じて参照される関数。

これらの理由により、コンパイラの裁量で、インライン展開が*他のユーザーのよう*に干渉する可能性があります。関数をインライン化するには、指定子に依存しないで **`inline`** ください。

通常の関数と同様に、インライン関数での引数の評価に対して定義された順序はありません。 実際には、通常の関数呼び出しプロトコルを使用して渡された場合、引数の評価順序とは異なる可能性があります。

[`/Ob`](../build/reference/ob-inline-function-expansion.md)コンパイラの最適化オプションは、インライン関数の拡張が実際に発生するかどうかを判断するのに役立ちます。

[`/LTCG`](../build/reference/ltcg-link-time-code-generation.md)ソースコードで要求されているかどうかにかかわらず、モジュール間のインライン展開を行います。

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

クラスのメンバー関数は、キーワードを使用するか、 **`inline`** または関数定義をクラス定義内に配置することによって、インラインで宣言できます。

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

**Microsoft 固有の仕様**

**`__inline`** キーワードはと同じです **`inline`** 。

でも **`__forceinline`** 、コンパイラはすべての状況でコードをインライン化できません。 次の場合、コンパイラは関数をインライン化できません。

- 関数またはその呼び出し元は、 **`/Ob0`** (デバッグビルドの既定のオプション) を使用してコンパイルされます。

- 関数と呼び出し元が、異なる種類の例外処理を使用する (一方は C++ 例外処理、他方は構造化例外処理)。

- 関数に可変個引数リストが含まれている。

- 関数は **`/Ox`** 、、、またはを使用してコンパイルされない限り、インラインアセンブリを使用し **`/O1`** **`/O2`** ます。

- 関数は再帰的であり、設定されていません **`#pragma inline_recursion(on)`** 。 プラグマによって、再帰関数はインライン展開され、既定の深さは 16 呼び出しになります。 インライン展開の深さを減らすには、プラグマを使用し [`inline_depth`](../preprocessor/inline-depth.md) ます。

- 関数が仮想で、仮想的に呼び出される。 仮想関数への直接呼び出しはインライン展開できます。

- プログラムが関数のアドレスを受け取り、関数へのポインターによって呼び出される。 受け取られるアドレスを持っている関数への直接呼び出しはインライン展開できます。

- 関数は、修飾子でもマークされ [`naked`](../cpp/naked-cpp.md) [`__declspec`](../cpp/declspec.md) ます。

コンパイラがで宣言された関数をインライン化できない場合は、 **`__forceinline`** 次の場合を除き、レベル1の警告が生成されます。

- 関数は、/Od または/ob0を使用してコンパイルされます。 このような場合、インライン展開は必要ありません。

- 関数は、外部、含まれているライブラリまたは別の翻訳単位で定義されているか、仮想呼び出しターゲットまたは間接呼び出しターゲットです。 コンパイラは、現在の翻訳単位では見つからない非インラインコードを識別できません。

再帰関数は、プラグマによって指定された深さのインラインコードに置き換えることができ [`inline_depth`](../preprocessor/inline-depth.md) ます。最大で16回の呼び出しが可能です。 その深さの後、再帰関数の呼び出しは、関数のインスタンスへの呼び出しとして扱われます。  インラインヒューリスティックによって再帰関数が検査される深さは、16を超えることはできません。 [`inline_recursion`](../preprocessor/inline-recursion.md)プラグマは、現在展開されている関数のインライン展開を制御します。 関連情報については、[インライン関数の展開](../build/reference/ob-inline-function-expansion.md)(/Ob) コンパイラオプションに関する説明を参照してください。

**Microsoft 固有の仕様はここまで**

指定子の使用方法の詳細については **`inline`** 、次を参照してください。

- [インライン クラス メンバー関数](../cpp/inline-functions-cpp.md)

- [Dllexport および dllimport を使用したインライン C++ 関数の定義](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>インライン関数を使用する状況

インライン関数は、プライベート データ メンバーにアクセスする関数のような小さな関数に使用するのが最適です。 これらの1つまたは2行の "アクセサー" 関数の主な目的は、オブジェクトに関する状態情報を返すことです。 短い関数は、関数呼び出しのオーバーヘッドに影響を受けます。 より長い関数は、呼び出し元と戻り値の時間を均等に短縮し、インライン展開よりも小さくなります。

クラスは次のように `Point` 定義できます。

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

このようなクラスのクライアントでは、座標の操作が比較的一般的な操作であると仮定します。通常、次のように2つのアクセサー関数 ( `x` `y` 前の例では) を指定して、オーバーヘッドを **`inline`** に保存します。

- 関数呼び出し (パラメーターの引き渡しおよびスタックへのオブジェクトのアドレスの配置を含む)

- 呼び出し元のスタック フレームの保持

- 新しいスタックフレームのセットアップ

- 戻り値のやり取り

- 古いスタックフレームを復元しています

- 戻り値

## <a name="inline-functions-vs-macros"></a>インライン関数とマクロ

インライン関数はマクロに似ています。関数コードは、コンパイル時に呼び出しの時点で展開されるためです。 ただし、インライン関数はコンパイラによって解析されるため、プリプロセッサによってマクロが拡張されます。 そのため、これらにはいくつかの重要な違いがあります。

- インライン関数は、通常の関数に適用されるタイプ セーフのすべてのプロトコルに従います。

- インライン関数は、関数宣言にキーワードが含まれていることを除いて、他の関数と同じ構文を使用して指定され **`inline`** ます。

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

式の目的は、 `toupper(getc(stdin))` コンソールデバイス () から文字を読み取って、 `stdin` 必要に応じて大文字に変換することです。

マクロの実装により、は、文字が "a" 以上であるかどうかを `getc` 判断するために1回実行され、"z" 以下であるかどうかを判断します。 入力文字がその範囲にある場合、`getc` が再実行されて、文字が大文字に変換されます。 これは、プログラムが 2 ~ 3 文字を待機しているときに、理想的には1つだけ待機することを意味します。

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

[`noinline`](../cpp/noinline.md)<br/>
[`auto_inline`](../preprocessor/auto-inline.md)
