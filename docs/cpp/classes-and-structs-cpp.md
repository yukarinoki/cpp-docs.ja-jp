---
title: クラスと構造体 (C++)
ms.date: 05/07/2019
helpviewer_keywords:
- C++, classes and structs
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
ms.openlocfilehash: 19d95c9519670db39f3ca467aff794233823d7ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180889"
---
# <a name="classes-and-structs-c"></a>クラスと構造体 (C++)

このセクションでは、C++ のクラスおよび構造体について説明します。 C++ においてこれらの 2 つのコンストラクトは、構造体では既定のアクセシビリティが "public" であるのに対してクラスでは "private" である点を除けば同じです。

クラスと構造体は、独自の型を定義するためのコンストラクトです。 クラスと構造体は、どちらもデータ メンバーとメンバー関数を含めることができ、これらを使用して型の状態や動作を説明できます。

次のトピックが含まれています。

- [class](../cpp/class-cpp.md)

- [struct](../cpp/struct-cpp.md)

- [クラス メンバーの概要](../cpp/class-member-overview.md)

- [メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)

- [継承](../cpp/inheritance-cpp.md)

- [静的メンバー](../cpp/static-members-cpp.md)

- [ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)

- [変更可能なデータメンバー (変更可能な指定子)](../cpp/mutable-data-members-cpp.md)

- [入れ子にされたクラス宣言](../cpp/nested-class-declarations.md)

- [匿名クラス型](../cpp/anonymous-class-types.md)

- [メンバーへのポインター](../cpp/pointers-to-members.md)

- [this ポインター](../cpp/this-pointer.md)

- [C++ ビット フィールド](../cpp/cpp-bit-fields.md)

3 つのクラス型は、構造体、クラス、および共用体です。 これらは、 [struct](../cpp/struct-cpp.md)、 [class](../cpp/class-cpp.md)、および[union](../cpp/unions.md)キーワードを使用して宣言されます。 次の表は、3 つのクラス型の違いを示しています。

共用体の詳細については、「[共用体](../cpp/unions.md)」を参照してください。 /Cli およびC++ C++/cx のクラスと構造体の詳細については、「[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>構造体、クラス、および共用体のアクセス制御と制約

|構造体|クラス|Unions|
|----------------|-------------|------------|
|クラスキーは**struct**です。|クラスキーは**クラス**です。|クラスキーは**union**です。|
|既定のアクセスは public|既定のアクセスは private|既定のアクセスは public|
|使用制約なし|使用制約なし|同時に複数のメンバーを使用することはできない|

## <a name="see-also"></a>参照

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)
