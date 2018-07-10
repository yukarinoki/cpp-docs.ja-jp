---
title: コピー コンス トラクターとコピー代入演算子 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- = operator [C++], copying objects
- assignment statements [C++], copying objects
- assignment operators [C++], for copying objects
- objects [C++], copying
- initializing objects, by copying objects
- copying objects
- assigning values to copy objects
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1292240e5343c461142e8c6029c277175f6a62f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417263"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>コピー コンストラクターとコピー代入演算子 (C++)
> [!NOTE]
>  C++ 11 以降、言語で 2 種類の代入はサポートされて:*コピー割り当て*と*移動代入*です。 この記事では、特に明示的に記載しない限り、"代入" はコピーの代入を意味します。 移動代入については、次を参照してください。[移動コンス トラクターと移動代入演算子 (C++)](http://msdn.microsoft.com/en-us/1442de5f-37a5-42a1-83a6-ec9cfe0414db)です。  
>   
>  代入演算と初期化操作では、いずれもオブジェクトがコピーされます。  
  
-   **割り当て**: 1 つのオブジェクトの値が別のオブジェクトに割り当てられていると、最初のオブジェクトが 2 番目のオブジェクトにコピーします。 次に例を示します。  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     の場合、`b` の値が `a` にコピーされます。  
  
-   **初期化**: 引数は、値によって関数に渡されるときに、新しいオブジェクトが宣言されたとき、または値が値によって関数から返されるときに初期化が行われます。  
  
 クラス型のオブジェクトに「コピー」の意味を定義できます。 たとえば、次のコードについて考えます。  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 前のコードは、「FILE1.DAT から FILE2.DAT に内容をコピーする」を意味する場合もありますが、「FILE2.DAT を無視して `b` を FILE1.DAT への 2 番目のハンドルにする」という意味もあります。 各クラスには、次のように適切なコピーのセマンティクスを割り当てる必要があります。  
  
-   戻り型としてのクラス型への参照と `operator=` 参照によって渡されるパラメーター (たとえば、`const`) と共に代入演算子 `ClassName& operator=(const ClassName& x);` を使用する。  
  
-   コピー コンストラクターを使用する。   
  
 コピー コンストラクターを宣言していない場合、コンパイラはメンバーごとのコピー コンストラクターを生成します。  コピー代入演算子を宣言していない場合、コンパイラはメンバーごとのコピー代入演算子を生成します。 コピー コンストラクターを宣言しても、コンパイラで生成されるコピー代入演算子は抑制されません。また、その逆も同様です。 いずれか 1 つを実装する場合、コードの意味を明確にするために、もう 1 つも実装することをお勧めします。  
   
 コピー コンス トラクターが型の引数を受け取る * クラス-名前 ***&** ここで、*クラス名*コンス トラクターが定義されているクラスの名前を指定します。 例えば:  
  
```cpp  
// spec1_copying_class_objects.cpp  
class Window  
{  
public:  
    Window( const Window& ); // Declare copy constructor.  
    // ...  
};  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  コピー コンス トラクターの引数の型を行う*const クラス-名前 * * * &** 可能な限りです。 これによって、コピー コンストラクターが誤ってコピー元のオブジェクトを変更しないようにすることができます。 コピーすることもできます**const**オブジェクト。  
  
## <a name="compiler-generated-copy-constructors"></a>コンパイラによって生成されたコピー コンストラクター  
 ユーザー定義のコピー コンス トラクターなど、コンパイラによって生成されたコピー コンス トラクターが型の単一の引数がある"への参照を*クラス名*"。 例外はすべての基底クラスとメンバーのクラス型の引数を 1 つとして宣言されたコピー コンス トラクターがある場合に**const** * クラス-名前 ***&** です。 このような場合は、コンパイラによって生成されたコピー コンス トラクターの引数も**const**です。  
  
 コピー コンス トラクターに引数の型がない場合**const**、コピーによる初期化を**const**オブジェクト、エラーが発生します。 逆は true ではありません: 引数の場合**const**ではないオブジェクトをコピーして初期化できます**const**です。  
  
 コンパイラによって生成された代入演算子、同じパターンに従いますに関して**const です。** 型の単一の引数を受け取りません*クラス-名前 * * * &** すべて基底クラスとメンバー クラスの代入演算子は、型の引数を受け取らない場合**const** *クラス名 (& a)。* クラスの代入演算子の受け取りを生成されたこのケースでは、 **const**引数。  
  
> [!NOTE]
>  コピー コンストラクターによって初期化されるか、コンパイラによって生成されるか、またはユーザーによって定義される場合、仮想基底クラスは構築される時点で 1 回だけ初期化されます。  
  
 影響はコピー コンストラクターの影響と似ています。 引数の型がない**const**からの割り当て、 **const**オブジェクト、エラーが発生します。 逆は true ではありません: 場合、 **const**ではない値に値が割り当てられている**const**、割り当てが成功します。  
  
 オーバー ロード代入演算子の詳細については、次を参照してください。[割り当て](../cpp/assignment.md)です。  
  
