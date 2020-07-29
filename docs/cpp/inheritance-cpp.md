---
title: 継承 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
ms.openlocfilehash: ab8425a916eb96f6419c67a76fa401716ad84631
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232262"
---
# <a name="inheritance--c"></a>継承 (C++)

このセクションでは、派生クラスを使用して拡張可能プログラムを生成する方法について説明します。

## <a name="overview"></a>概要

"継承" と呼ばれる機構を使用して、既存のクラスから新しいクラスを派生させることができます (「[単一継承](../cpp/single-inheritance.md)」の情報を参照してください)。 派生に使用されるクラスは、特定の派生クラスの "基底クラス" と呼ばれます。 派生クラスは、次の構文を使用して宣言します。

```cpp
class Derived : [virtual] [access-specifier] Base
{
   // member list
};
class Derived : [virtual] [access-specifier] Base1,
   [virtual] [access-specifier] Base2, . . .
{
   // member list
};
```

クラスのタグ (名前) の後ろにコロンを指定し、その後ろに基本指定のリストが続きます。  したがって、基底クラスは、あらかじめ宣言しておく必要があります。  基本仕様には、キーワード、またはのいずれかであるアクセス指定子を含めることができ **`public`** **`protected`** **`private`** ます。  これらのアクセス指定子は、基底クラス名の前に指定され、その基底クラスにのみ適用されます。  これらの指定子は、派生クラスで基底クラスのメンバーに対して使用されるアクセス許可を制御します。  基底クラスのメンバーへのアクセスについては[、「メンバー Access Control](../cpp/member-access-control-cpp.md) 」を参照してください。  アクセス指定子が省略されている場合、そのベースへのアクセスは考慮され **`private`** ます。  基本仕様には、 **`virtual`** 仮想継承を示すキーワードを含めることができます。  このキーワードがある場合は、アクセス指定子の前または後に指定されます。  仮想継承を使用する場合、基底クラスは、仮想基底クラスと呼ばれます。

複数の基底クラスをコンマで区切って指定できます。  1つの基底クラスが指定されている場合、継承モデルは[単一継承](../cpp/single-inheritance.md)です。複数の基底クラスが指定されている場合、継承モデルは[多重継承](../cpp/multiple-base-classes.md)と呼ばれます。

次のトピックが含まれています。

- [単一継承](../cpp/single-inheritance.md)

- [複数の基本クラス](../cpp/multiple-base-classes.md)

- [仮想関数](../cpp/virtual-functions.md)

- [明示的なオーバーライド](../cpp/explicit-overrides-cpp.md)

- [抽象クラス](../cpp/abstract-classes-cpp.md)

- [スコープ規則の概要](../cpp/summary-of-scope-rules.md)

[__Super](../cpp/super.md)キーワードと[__interface](../cpp/interface.md)キーワードについては、このセクションで説明します。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)
