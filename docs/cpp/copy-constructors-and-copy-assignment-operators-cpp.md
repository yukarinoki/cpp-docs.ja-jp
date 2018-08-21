---
title: コピー コンス トラクターとコピー代入演算子 (C++) |Microsoft Docs
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
ms.openlocfilehash: 24f9e4e5b3d157f23c18d46f2857b29e6960e82e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405757"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>コピー コンストラクターとコピー代入演算子 (C++)
> [!NOTE]
>  C++ 11 以降、2 種類の代入が言語でサポートされて:*コピー割り当て*と*移動の代入*します。 この記事では、特に明示的に記載しない限り、"代入" はコピーの代入を意味します。 移動代入については、次を参照してください。[移動コンス トラクターと移動代入演算子 (C++)](http://msdn.microsoft.com/1442de5f-37a5-42a1-83a6-ec9cfe0414db)します。  
>   
>  代入演算と初期化操作では、いずれもオブジェクトがコピーされます。  
  
-   **割り当て**: 最初のオブジェクトが 2 番目のオブジェクトにコピーが 1 つのオブジェクトの値が別のオブジェクトに割り当てられると、します。 次に例を示します。  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     の場合、`b` の値が `a` にコピーされます。  
  
-   **初期化**: 初期化は、引数は、値によって関数に渡されるときに、新しいオブジェクトが宣言されたとき、または値が値によって関数から返されるときに発生します。  
  
 クラス型のオブジェクトに「コピー」の意味を定義できます。 たとえば、次のコードについて考えます。  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 前のコードは、「FILE1.DAT から FILE2.DAT に内容をコピーする」を意味する場合もありますが、「FILE2.DAT を無視して `b` を FILE1.DAT への 2 番目のハンドルにする」という意味もあります。 各クラスには、次のように適切なコピーのセマンティクスを割り当てる必要があります。  
  
-   代入演算子を使用して**演算子 =** 戻り値の型として渡されるパラメーターとしてクラス型への参照と共に**const**参照 — たとえば`ClassName& operator=(const ClassName& x);`します。  
  
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
>  コピー コンス トラクターの引数の型を行う*const クラス-名前 * * * &** 可能であれば。 これによって、コピー コンストラクターが誤ってコピー元のオブジェクトを変更しないようにすることができます。 コピーすることもできます**const**オブジェクト。  
  
## <a name="compiler-generated-copy-constructors"></a>コンパイラによって生成されたコピー コンストラクター  
 ユーザー定義のコピー コンス トラクターのように、コンパイラによって生成されたコピー コンス トラクターがある型の 1 つの引数"への参照*クラス名*"。 すべての基底クラスとメンバーのクラス型の 1 つの引数の取得として宣言されたコピー コンス トラクターがある場合は、例外**const** * クラス-名前 ***&** します。 このような場合は、コンパイラによって生成されたコピー コンス トラクターの引数も**const**します。  
  
 コピー コンス トラクターに引数の型がない場合**const**、コピーによる初期化を**const**オブジェクト、エラーが発生します。 逆はできません: 引数が場合**const**、初期化するにはないオブジェクトのコピーで**const**。  
  
 コンパイラによって生成された代入演算子に関して同じパターンに従います**const です。** 型の 1 つの引数をとる*クラス-名前 * * * &** すべて基底クラスおよびメンバー クラスの代入演算子は、型の引数を受け取らない**const** *クラス名 (& a)。* クラスの代入演算子を生成されたここで、 **const**引数。  
  
> [!NOTE]
>  コピー コンストラクターによって初期化されるか、コンパイラによって生成されるか、またはユーザーによって定義される場合、仮想基底クラスは構築される時点で 1 回だけ初期化されます。  
  
 影響はコピー コンストラクターの影響と似ています。 引数の型がない**const**からの割り当て、 **const**オブジェクト、エラーが発生します。 逆はできません: 場合、 **const**値がない値に割り当てられている**const**割り当てが成功するとします。  
  
 オーバー ロードされた代入演算子の詳細については、次を参照してください。[割り当て](../cpp/assignment.md)します。  