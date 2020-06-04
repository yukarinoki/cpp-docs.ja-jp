---
title: '値のカテゴリ: 左辺値と右辺値C++()'
ms.date: 05/07/2019
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
ms.openlocfilehash: 23625ddf44d16a4dc408b87f27b9cdfba7a9cbd4
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077233"
---
# <a name="lvalues-and-rvalues-c"></a>左辺値と右辺値 (C++)

すべてC++の式には型があり、*値カテゴリ*に属しています。 値のカテゴリは、式の評価中に一時オブジェクトを作成、コピー、および移動するときに、コンパイラが従う必要のある規則の基礎となります。

C++ 17 標準では、式の値のカテゴリは次のように定義されています。

- *Glvalue*は、オブジェクト、ビットフィールド、または関数の id を評価する式です。
- *Prvalue*は、オブジェクトまたはビットフィールドを初期化する評価を持つ式です。または、演算子のオペランドの値を、表示されるコンテキストによって指定されたとおりに計算します。
- *Xvalue*は、リソースを再利用できるオブジェクトまたはビットフィールドを示す glvalue です (通常は、有効期間が終了しているため)。 例: 右辺値参照 (8.3.2) を含む特定の種類の式では、戻り値の型が右辺値参照または右辺値参照型へのキャストである関数の呼び出しなど、xvalues が生成されます。
- *左辺*値は、xvalue ではない glvalue です。
- *右辺*値は、prvalue または xvalue です。

次の図は、カテゴリ間の関係を示しています。

![C++式の値のカテゴリ](media/value_categories.png "C++式の値のカテゴリ")

左辺値には、プログラムがアクセスできるアドレスがあります。 左辺値式の例としては、**定数**変数、配列要素、左辺値参照を返す関数呼び出し、ビットフィールド、共用体、クラスメンバーなどがあります。

Prvalue 式には、プログラムからアクセスできるアドレスがありません。 Prvalue 式の例としては、リテラル、非参照型を返す関数呼び出し、式の評価中に作成され、コンパイラだけがアクセスできる一時オブジェクトなどがあります。

Xvalue 式には、プログラムからアクセスできなくなったアドレスがありますが、右辺値参照を初期化するために使用できます。これにより、式へのアクセスが可能になります。 例としては、右辺値参照を返す関数呼び出し、配列の添字、メンバー、および配列またはオブジェクトが右辺値参照であるメンバー式へのポインターがあります。

## <a name="example"></a>例

次の例は、左辺値と右辺値の正しい使用方法と間違った使用方法のいくつかを示しています。

```cpp
// lvalues_and_rvalues2.cpp
int main()
{
    int i, j, *p;

    // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.
    i = 7;

    // Incorrect usage: The left operand must be an lvalue (C2106).`j * 4` is a prvalue.
    7 = i; // C2106
    j * 4 = 7; // C2106

    // Correct usage: the dereferenced pointer is an lvalue.
    *p = i;

    // Correct usage: the conditional operator returns an lvalue.
    ((i < 3) ? i : j) = 7;

    // Incorrect usage: the constant ci is a non-modifiable lvalue (C3892).
    const int ci = 7;
    ci = 9; // C3892
}
```

> [!NOTE]
> このトピックの例では、演算子がオーバーロードしていないときの、正しい方法使用と正しくない使用方法を説明します。 演算子をオーバーロードすることにより、`j * 4` のような式を左辺値にできます。

*左辺*値と*右辺*値は、オブジェクト参照を参照するときによく使用されます。 参照の詳細については、「[左辺値参照宣言](../cpp/lvalue-reference-declarator-amp.md)子: &」および「[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="see-also"></a>参照

[基本的な概念](../cpp/basic-concepts-cpp.md)<br/>
[左辺値参照宣言子: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)
