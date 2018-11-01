---
title: 属性 (C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 13a2639a877d1ba926d74511addcf72763967d85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462245"
---
# <a name="attributes-ccx"></a>属性 (C++/CX)

属性は、メタデータ作成で特定の動作を指定するには、Windows ランタイム型とメソッドの角かっこの前に付加する ref クラスの特殊なです。 複数の属性の定義済み — たとえば、 [Windows::Foundation::Metadata::WebHostHidden](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)-C + でよく使用される/cli/CX コード。 この例では、属性がクラスに適用される方法を示します。

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>カスタム属性

カスタム属性も定義できます。 カスタム属性は、Windows ランタイムのこれらの規則に従う必要があります。

- カスタム属性は、パブリック フィールドだけを格納できます。

- カスタム属性フィールドは、属性がクラスに適用されるときに初期化できます。

- フィールドは、次に示すいずれかの型になることができます。

   - int32 (int)

   - uint32 (unsigned int)

   - bool

   - Platform::String^

   - Windows::Foundation::HResult

   - Platform::Type^

   - パブリック列挙型クラス (ユーザー定義列挙型を含む)

次の例では、カスタム属性を定義し、使用時に初期化する方法を示します。

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>関連項目

[型システム (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間参照](../cppcx/namespaces-reference-c-cx.md)