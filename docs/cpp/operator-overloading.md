---
title: 演算子のオーバーロード
ms.date: 11/04/2016
f1_keywords:
- operator_cpp
- operator
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
ms.openlocfilehash: a16f68088ffffd6c3cf38f5ae3adda5f2d59fb57
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188572"
---
# <a name="operator-overloading"></a>演算子のオーバーロード

**Operator**キーワードは、クラスのインスタンスに適用されるときに、*演算子記号*を指定する関数を宣言します。 これによって、演算子に複数の意味を与えます (つまり、"オーバーロード" します)。 コンパイラは、オペランドの型を検査することにより、演算子の異なる意味を区別します。

## <a name="syntax"></a>構文

> *型***演算子***演算子-symbol* **(** *パラメーターリスト* **)**

## <a name="remarks"></a>解説

ほとんどの組み込み演算子の関数をグローバルに、またはクラス単位で定義し直すことができます。 オーバーロードされた演算子は、関数として実装されます。

オーバーロードされた演算子の名前は**operator** *x*です。ここで、 *x*は次の表に示す演算子です。 たとえば、加算演算子をオーバーロードするには、 **operator +** という関数を定義します。 同様に、加算/代入演算子をオーバーロードするには、 **+=** 、 **operator + =** という関数を定義します。

### <a name="redefinable-operators"></a>再定義可能な演算子

|演算子|Name|種類|
|--------------|----------|----------|
|**、**|コンマ|Binary|
|**!**|論理 NOT|単項演算子|
|**!=**|非等値|Binary|
|**%**|Modulus|Binary|
|**%=**|剰余代入|Binary|
|**&**|ビット演算子 AND|Binary|
|**&**|アドレス取得|単項演算子|
|**&&**|論理積|Binary|
|**&=**|ビットごとの AND 代入|Binary|
|**( )**|関数呼び出し|—|
|**( )**|キャスト演算子|単項演算子|
|**&#42;**|乗算|Binary|
|**&#42;**|ポインター逆参照|単項演算子|
|**&#42;=**|乗算代入|Binary|
|**+**|加算|Binary|
|**+**|単項プラス|単項演算子|
|**++**|インクリメント<sup>1</sup>|単項演算子|
|**+=**|加算代入|Binary|
|**-**|減算|Binary|
|**-**|単項マイナス符号|単項演算子|
|**--**|デクリメント<sup>1</sup>|単項演算子|
|**-=**|減算代入|Binary|
|**->**|メンバー選択|Binary|
|**->&#42;**|メンバーへのポインター選択|Binary|
|**/**|除算|Binary|
|**/=**|除算代入|Binary|
|**\<**|より小さい|Binary|
|**<<**|左シフト|Binary|
|**<<=**|左シフト代入|Binary|
|**<=**|以下|Binary|
|**=**|割り当て|Binary|
|**==**|等式|Binary|
|**>**|より大きい|Binary|
|**>=**|以上|Binary|
|**>>**|右シフト|Binary|
|**>>=**|右シフト代入|Binary|
|**[ ]**|配列インデックス|—|
|**^**|排他的 OR|Binary|
|**^=**|排他的 OR 代入|Binary|
|**&#124;**|ビット演算子包含的 OR|Binary|
|**&#124;=**|ビットごとの包括的 OR 代入|Binary|
|**&#124;&#124;**|論理和|Binary|
|**~**|1 の補数|単項演算子|
|**delete**|削除|—|
|**新規**|新規|—|
|変換演算子|変換演算子|単項演算子|

<sup>1</sup>単項インクリメント演算子とデクリメント演算子の2つのバージョンが存在します: 前置インクリメントと後置インクリメント。

詳細については、「[演算子のオーバーロードに関する一般的な規則](../cpp/general-rules-for-operator-overloading.md)」を参照してください。 さまざまなカテゴリのオーバーロードされた演算子に対する制約については、次のトピックを参照してください。

- [単項演算子](../cpp/overloading-unary-operators.md)

- [二項演算子](../cpp/binary-operators.md)

- [割り当て](../cpp/assignment.md)

- [関数呼び出し](../cpp/function-call-cpp.md)

- [添字演算子](../cpp/subscripting.md)

- [クラスメンバーアクセス](../cpp/member-access.md)

- [インクリメントとデクリメント](../cpp/increment-and-decrement-operator-overloading-cpp.md)。

- [ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)

次のテーブルに示す演算子は、オーバーロードできません。 この表には、プリプロセッサシンボル **#** および **##** が含まれています。

### <a name="nonredefinable-operators"></a>再定義不可演算子

|演算子|Name|
|-|-|
|**」を参照してください。**|メンバー選択|
|**.&#42;**|メンバーへのポインター選択|
|**::**|スコープ解決|
|**? :**|条件付き|
|**#**|プリプロセッサによる文字列への変換|
|**##**|プリプロセッサによる連結|

オーバーロードされた演算子は通常、コードに出現すると、コンパイラによって暗黙的に呼び出されますが、メンバーまたは非メンバー関数を呼び出すのと同じ方法で明示的に呼び出すことができます。

```cpp
Point pt;
pt.operator+( 3 );  // Call addition operator to add 3 to pt.
```

## <a name="example"></a>例

次の例では、 **+** 演算子をオーバーロードして2つの複素数を加算し、その結果を返します。

```cpp
// operator_overloading.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct Complex {
   Complex( double r, double i ) : re(r), im(i) {}
   Complex operator+( Complex &other );
   void Display( ) {   cout << re << ", " << im << endl; }
private:
   double re, im;
};

// Operator overloaded using a member function
Complex Complex::operator+( Complex &other ) {
   return Complex( re + other.re, im + other.im );
}

int main() {
   Complex a = Complex( 1.2, 3.4 );
   Complex b = Complex( 5.6, 7.8 );
   Complex c = Complex( 0.0, 0.0 );

   c = a + b;
   c.Display();
}
```

```Output
6.8, 11.2
```

## <a name="in-this-section"></a>このセクションの内容

- [演算子のオーバーロードに関する一般的な規則](../cpp/general-rules-for-operator-overloading.md)

- [単項演算子のオーバーロード](../cpp/overloading-unary-operators.md)

- [二項演算子](../cpp/binary-operators.md)

- [割り当て](../cpp/assignment.md)

- [関数呼び出し](../cpp/function-call-cpp.md)

- [添字演算子](../cpp/subscripting.md)

- [メンバー アクセス](../cpp/member-access.md)

## <a name="see-also"></a>参照

[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
