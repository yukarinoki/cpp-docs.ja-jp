---
title: コンパイラ エラー C2143 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 076f2ccb594edd5d9e627d8a4dcea2d9bb928890
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2143"></a>コンパイラ エラー C2143
構文エラー: 'token2 'が見つかりましたする前に ' token1' がありません  
  
 コンパイラは、特定のトークン (空白以外の言語要素) が必要し、代わりにトークンが検出されました。  
  
 このエラーについては関数 try ブロックを使用している場合を参照してください[サポート技術情報の記事 241706](http://support.microsoft.com/kb/241706)です。  
  
 チェック、 [C++ 言語リファレンス](../../cpp/cpp-language-reference.md)コードが構文的に正しいかを判断します。 コンパイラは、問題の原因となる行を検出した後、このエラーを報告可能性があります、ため、エラーの前にいくつかの行のコードを確認してください。  
  
 C2143 は、さまざまな状況で発生することができます。  
  
 場合、名前を修飾する演算子に発生することができます (`::`、 `->`、および`.`) キーワードが続かなければなりません`template`この例のように。  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 既定では、C++ であると推定`Ty::PutFuncType`; テンプレートではありません、次にそのため、`<`小として解釈されます-不等号です。  必要がありますコンパイラに通知する明示的にいる`PutFuncType`テンプレートは、山かっこを正しく解析することができるようにします。 このエラーを解決するには、`template`依存する型の名前を次に示すようにキーワード。  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 エラーが発生することがときに **/clr**を使用し、`using`ディレクティブは、構文エラー。  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 使用せず、CLR の構文を使用して、ソース コード ファイルをコンパイルしようとしているときにも発生 **/clr**:  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 これに続く最初の空白以外の文字、`if`ステートメントは、左かっこをする必要があります。 コンパイラは、何を変換できません。  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143、終わりかっこ、かっこ、またはセミコロンが、エラーが検出された行に不足している場合に発生したり、行の 1 つ上の真上します。  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 または、クラス宣言に無効なタグが存在する場合。  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 または、ステートメントには、ラベルはアタッチされていない場合。 場合単独でラベルを配置する必要があります、たとえば、複合ステートメントの最後にアタッチ null ステートメント。  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 エラーは、C++ 標準ライブラリ内の型を修飾されていない呼び出しが行われたときに発生します。  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 見つからないまたは`typename`キーワード。  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 または、明示的なインスタンス化を定義しようとする場合。  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 C プログラムでは、関数の先頭に変数を宣言する必要があり、関数宣言以外の手順の実行後にこれらを宣言することはできません。  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  
