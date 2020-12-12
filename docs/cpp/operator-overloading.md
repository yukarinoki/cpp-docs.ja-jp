---
description: '詳細情報: 演算子のオーバーロード'
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
ms.openlocfilehash: 23a35a87f9f370a9bb8f268ac1637a4a899ee5f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146030"
---
# <a name="operator-overloading"></a>演算子のオーバーロード

キーワードは、 **`operator`** クラスのインスタンスに適用されるときに、 *演算子記号* を指定する関数を宣言します。 これによって、演算子に複数の意味を与えます (つまり、"オーバーロード" します)。 コンパイラは、オペランドの型を検査することにより、演算子の異なる意味を区別します。

## <a name="syntax"></a>構文

> *型* **`operator`***operator-symbol* **(** *パラメーターリスト* **)**

## <a name="remarks"></a>解説

ほとんどの組み込み演算子の関数をグローバルに、またはクラス単位で定義し直すことができます。 オーバーロードされた演算子は、関数として実装されます。

オーバーロードされた演算子の名前は **`operator`** *x* です。ここで、 *x* は次の表に示すように演算子です。 たとえば、加算演算子をオーバーロードするには、 **operator +** という関数を定義します。 同様に、加算/代入演算子をオーバーロードするには、 **+=** **operator + =** という関数を定義します。

### <a name="redefinable-operators"></a>再定義可能な演算子

|演算子|名前|Type|
|--------------|----------|----------|
|**,**|コンマ|2 項|
|**!**|論理 NOT|単項|
|**!=**|不等式|2 項|
|**%**|剰余|2 項|
|**%=**|剰余代入|2 項|
|**&**|ビット演算子 AND|2 項|
|**&**|アドレス取得|単項|
|**&&**|論理積|2 項|
|**&=**|ビットごとの AND 代入|2 項|
|**( )**|関数呼び出し|—|
|**( )**|キャスト演算子|単項|
|**&#42;**|乗算|2 項|
|**&#42;**|ポインター逆参照|単項|
|**&#42;=**|乗算代入|2 項|
|**+**|加算|2 項|
|**+**|単項プラス|単項|
|**++**|インクリメント <sup>1</sup>|単項|
|**+=**|加算代入|2 項|
|**-**|減算|2 項|
|**-**|単項マイナス符号|単項|
|**--**|デクリメント <sup>1</sup>|単項|
|**-=**|減算代入|2 項|
|**->**|メンバー選択|2 項|
|**->&#42;**|メンバーへのポインター選択|2 項|
|**/**|事業部|2 項|
|**/=**|除算代入|2 項|
|**\<**|より小さい|2 項|
|**<<**|左シフト|2 項|
|**<<=**|左シフト代入|2 項|
|**<=**|以下|2 項|
|**=**|割り当て|2 項|
|**==**|等式|2 項|
|**>**|より大きい|2 項|
|**>=**|以上|2 項|
|**>>**|右シフト|2 項|
|**>>=**|右シフト代入|2 項|
|**[ ]**|配列インデックス|—|
|**^**|排他的 OR|2 項|
|**^=**|排他的 OR 代入|2 項|
|**&#124;**|ビット演算子包含的 OR|2 項|
|**&#124;=**|ビットごとの包括的 OR 代入|2 項|
|**&#124;&#124;**|論理和|2 項|
|**~**|1 の補数|単項|
|**`delete`**|削除|—|
|**`new`**|新規作成|—|
|変換演算子|変換演算子|単項|

<sup>1</sup> 単項インクリメント演算子とデクリメント演算子の2つのバージョンが存在します: 前置インクリメントと後置インクリメント。

詳細については、「 [演算子のオーバーロードに関する一般的な規則](../cpp/general-rules-for-operator-overloading.md) 」を参照してください。 さまざまなカテゴリのオーバーロードされた演算子に対する制約については、次のトピックを参照してください。

- [単項演算子](../cpp/overloading-unary-operators.md)

- [二項演算子](../cpp/binary-operators.md)

- [割り当て](../cpp/assignment.md)

- [関数呼び出し](../cpp/function-call-cpp.md)

- [添字演算子](../cpp/subscripting.md)

- [クラス メンバーに対するアクセス](../cpp/member-access.md)

- [インクリメントとデクリメント](../cpp/increment-and-decrement-operator-overloading-cpp.md)。

- [ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)

次のテーブルに示す演算子は、オーバーロードできません。 この表には、プリプロセッサシンボルとが含まれてい **#** **##** ます。

### <a name="nonredefinable-operators"></a>再定義不可演算子

|演算子|名前|
|-|-|
|**.**|メンバー選択|
|**. &#42;**|メンバーへのポインター選択|
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

次の例では、演算子をオーバーロードして **+** 2 つの複素数を加算し、その結果を返します。

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

- [メンバーアクセス](../cpp/member-access.md)

## <a name="see-also"></a>関連項目

[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
