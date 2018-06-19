---
title: 'カテゴリの値: 左辺値と右辺値 (Visual C) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bbe048ee6667aaf71b2a3cf52e82993f90ab1c7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419142"
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalue と Rvalue (Visual C)

すべての C++ 式の型に属している、*値カテゴリ*です。 値のカテゴリは、コンパイラが作成、コピー、および式の評価中に一時オブジェクトを移動するときに従う必要があるルールの基礎です。

 C++ 17 規格では、式の値のカテゴリは次のように定義されています。

- A *glvalue*の評価、ビット フィールド、または関数オブジェクトの id を決定する式を指定します。
- A *prvalue*の評価をオブジェクトまたはビット フィールドを初期化またはで次のように表示されます。 コンテキストで指定されたように、演算子のオペランドの値を計算式を指定します。
- *Xvalue*オブジェクトまたはビット フィールド (通常になっているため、有効期間の終わりに近い) に再利用できるリソースが示す glvalue がします。 [例: 右辺値参照 (8.3.2) を含む式は、特定の種類は、戻り値の型が右辺値参照関数の呼び出しまたは参照型 rvalue へのキャストなどの取得を生成します。 ]
- *左辺値*れていない、xvalue glvalue がします。
- *右辺値*prvalue または xvalue にします。

次の図は、カテゴリ間の関係を示しています。

 ![C++ 式の値のカテゴリ](media/value_categories.png "C++ 式の値のカテゴリ")

 左辺値では、プログラムにアクセスできるアドレスがあります。 左辺値式の例として、変数名を含む`const`変数、配列要素、関数呼び出しの左辺値参照、ビット フィールド、共用体、およびクラス メンバーを返すことです。

 Prvalue 式には、プログラムからアクセス可能なアドレスがありません。 Prvalue 式の例には、リテラル、非参照型を返す関数呼び出しと、コンパイラによってのみアクセスできますが、式の評価中に作成される一時オブジェクトが含まれます。

 Xvalue 式がアドレスをプログラムでアクセス不可能になってが式へのアクセスを提供する、右辺値参照を初期化するために使用できます。 例には、戻り値の右辺値参照、配列の添字、メンバーおよびポインター メンバー式に、配列またはオブジェクトが右辺値参照を関数呼び出しが含まれます。

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

 const int ci = 7;
 // Incorrect usage: the variable is a non-modifiable lvalue (C3892).
 ci = 9; // C3892

 // Correct usage: the conditional operator returns an lvalue.
 ((i < 3) ? i : j) = 7;
}
```

> [!NOTE]
> このトピックの例では、演算子がオーバーロードしていないときの、正しい方法使用と正しくない使用方法を説明します。 演算子をオーバーロードすることにより、`j * 4` のような式を左辺値にできます。

条項*左辺値*と*右辺値*はオブジェクト参照を参照するときに、よく使用します。 参照の詳細については、次を参照してください。[左辺値参照宣言子: &](../cpp/lvalue-reference-declarator-amp.md)と[右辺値参照宣言子: & (& a)](../cpp/rvalue-reference-declarator-amp-amp.md)です。

## <a name="see-also"></a>関連項目

 [基本的な概念](../cpp/basic-concepts-cpp.md)[左辺値参照宣言子: &](../cpp/lvalue-reference-declarator-amp.md) [右辺値参照宣言子: & (& a)](../cpp/rvalue-reference-declarator-amp-amp.md)