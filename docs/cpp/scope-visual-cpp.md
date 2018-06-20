---
title: スコープ (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/08/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e79ae7f861553ce2bcd7bee6cbb14a3c2965d4ce
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261085"
---
# <a name="scope-c"></a>スコープ (C)

クラス、関数、または変数などのプログラム要素を宣言する場合の名前のみ「表示」して、プログラムの特定の部分で使用します。 名前が表示されているコンテキストが呼び出されたその*スコープ*です。 変数を宣言する場合など、`x`関数の内部`x`はのみその関数の本体内で表示します。 *ローカル スコープ*です。 プログラムで、同じ名前で他の変数がある可能性がありますさまざまなスコープでは、限り、単一定義規則に違反しないし、エラーは発生しません。

自動の非静的変数のスコープに作成されプログラム実行用メモリ内の破棄されたのともを決定します。 

スコープの 6 つの種類があります。

- **グローバル スコープ**グローバル名は、任意のクラス、関数または名前空間の外部で宣言されているいずれか。 ただし、C++ では、暗黙的なグローバル名前空間を持つにもこれらの名前が存在します。 グローバルな名前のスコープは、宣言されているファイルの末尾を宣言の時点から適用されます。 グローバルな名前の可視性が適用されていますの規則[リンケージ](program-and-linkage-cpp.md)名前は、プログラムの他のファイルに表示するかどうかを指定します。

- **Namespace スコープ**内で宣言された名前、[名前空間](namespaces-cpp.md)、任意のクラスまたは列挙型の定義または関数ブロックの外部では名前空間の末尾には、宣言の位置から表示します。 名前空間は、異なるファイル間で複数のブロックで定義することがあります。

- **ローカル スコープ**関数またはパラメーターの名前も含め、ラムダ内で宣言された名前はローカル スコープを設定します。 参照されている多くの場合に「ローカル」とします。 のみ関数またはラムダ本体の末尾に、宣言の位置から表示されます。 ローカル スコープは、この記事の後半で説明する、ブロック スコープの種類です。

- **クラス スコープ**クラス メンバーの名前は、宣言の位置に関係なく、クラス定義が終わるときまでクラス スコープを持ちます。 クラス メンバーのアクセシビリティは名前空間によって制御される、**パブリック**、**プライベート**、および**保護**キーワード。 パブリックまたはプロテクト メンバーにのみ、メンバー選択演算子を使用してアクセスできます (**です。** または**->**) またはメンバーへのポインター演算子 (**.\*** または**-> \***)。

- **ステートメントのスコープ**で宣言された名前、**の**、**場合**、**中**、または**切り替える**ステートメントが終了するまで表示、ステートメント ブロックします。

- **関数スコープ**A[ラベル](labeled-statements.md)関数のスコープは、そのポイント宣言の前でもに、、関数本体全体で可視であることを意味します。 関数スコープなどのステートメントを記述することが`goto cleanup`する前に、`cleanup`ラベルを宣言します。

## <a name="hiding-names"></a>名前の隠ぺい

囲まれたブロック内で名前を宣言すると、その名前が非表示になります。 次の図では、内側のブロックで `i` が再宣言されています。そのため、外側のブロック スコープでは `i` に関連付けられた変数が隠し変数になります。

 ![ブロック&#45;スコープの名前の隠ぺい](../cpp/media/vc38sf1.png "vc38SF1")ブロック スコープおよび名前の非表示にします。

 このプログラムの出力を次の図に示します。

```cpp
i = 0
i = 7
j = 9
i = 0
```

> [!NOTE]
> `szWhat` 引数は、この関数のスコープ内にあると見なされます。 したがって、この関数の外側のブロックで宣言されたものとして処理されます。

## <a name="hiding-class-names"></a>クラス名の非表示

 関数、オブジェクト、変数、または列挙子を同じスコープ内で宣言することで、クラス名を非表示にできます。 ただし、クラス名アクセスできますキーワードで始まるとき**クラス**です。

```cpp
// hiding_class_names.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

// Declare class Account at global scope.
class Account
{
public:
    Account( double InitialBalance )
        { balance = InitialBalance; }
    double GetBalance()
        { return balance; }
private:
    double balance;
};

double Account = 15.37;            // Hides class name Account

int main()
{
    class Account Checking( Account ); // Qualifies Account as 
                                       //  class name

    cout << "Opening account with balance of: "
         << Checking.GetBalance() << "\n";
}
//Output: Opening account with balance of: 15.37
```

> [!NOTE]
> 任意の場所、クラス名 (`Account`) を呼び出すときは、class キーワードは、グローバル スコープ変数 Account と区別するために使用する必要があります。 スコープ解決演算子 (::) の左側がクラス名の場合は、この規則が適用されません。 スコープ解決演算子の左側の名前は、常にクラス名と見なされます。

 次の例は、型のオブジェクトへのポインターを宣言する方法を示します`Account`を使用して、**クラス**キーワード。

```cpp
class Account *Checking = new class Account( Account );
```

 `Account` (かっこ内) 上記のステートメントで初期化子ではグローバル スコープ以外の型である**二重**です。

> [!NOTE]
> この例のように、識別子名を再使用するのは適切なプログラミング方法ではありません。

 ポインターの詳細については、次を参照してください。[派生型](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c)です。 クラスのオブジェクトの宣言と初期化については、次を参照してください。[クラス、構造、および共用体](../cpp/classes-and-structs-cpp.md)です。 使用方法について、**新しい**と**削除**フリー ストア演算子を参照してください[新しい演算子と delete 演算子](new-and-delete-operators.md)です。

## <a name="hiding-names-with-global-scope"></a>グローバル スコープを持つ名前を非表示にします。

 ブロック スコープ内の同じ名前を明示的に宣言してグローバル スコープを持つ名前を非表示にすることができます。 スコープ解決演算子を使用してグローバル スコープ名にアクセスできますが、(`::`)。

```cpp
#include <iostream>

int i = 7;   // i has global scope, outside all blocks
using namespace std;

int main( int argc, char *argv[] ) {
   int i = 5;   // i has block scope, hides i at global scope
   cout << "Block-scoped i has the value: " << i << "\n";
   cout << "Global-scoped i has the value: " << ::i << "\n";
}
```

```Output
Block-scoped i has the value: 5
Global-scoped i has the value: 7
```

## <a name="see-also"></a>関連項目

 [基本的な概念](../cpp/basic-concepts-cpp.md)