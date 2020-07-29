---
title: 列挙型 (C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: 54e413e65b3130b9b83e6d1ed56b5ee87b84e0a3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225762"
---
# <a name="enums-ccx"></a>列挙型 (C++/CX)

C++/CX では、 `public enum class` 標準 c++ に似たキーワードがサポートされてい `scoped  enum` ます。 `public enum class` キーワードを使用して宣言された列挙子を使用する場合、列挙体識別子を使用して各列挙子値の範囲を指定する必要があります。

### <a name="remarks"></a>解説

などの `public enum class` アクセス指定子を持たないは、 **`public`** 標準 C++[スコープ列挙型](../cpp/enumerations-cpp.md)として扱われます。

`public enum class`またはの宣言は、 `public enum struct` 任意の整数型の基になる型を持つことができますが、Windows ランタイム自体は型を int32 にする必要がありますが、flags 列挙型の場合は uint32 です。 次の構文は、 `public enum class` または `public enum struct`の各部分を説明します。

この例は、パブリック列挙型クラスを定義する方法を示しています。

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

この次の例では、それを利用する方法を示しています。

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>例

次の例は、列挙型を宣言する方法を示します。

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

次の例は、同等の数値にキャストし、比較を実行する方法を示しています。 列挙子 `One` の使用範囲は `Enum1` 列挙体識別子により指定され、列挙子 `First` の範囲は `Enum2`によって指定されることに注意してください。

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>関連項目

[型システム](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
