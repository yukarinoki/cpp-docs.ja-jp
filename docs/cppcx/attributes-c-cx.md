---
description: '詳細: 属性 (C++/CX)'
title: 属性 (C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 82299db6b5c11521584b8dd400b401ec0df78c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302778"
---
# <a name="attributes-ccx"></a>属性 (C++/CX)

属性とは、特殊な種類の ref クラスであり、角かっこで囲んで、メタデータの作成時に特定の動作を指定するための型とメソッドを Windows ランタイムできます。 C++/CX コードでは、いくつかの定義済み属性 (  [Windows:: Foundation:: Metadata:: WebHostHidden](/uwp/api/windows.foundation.metadata.webhosthiddenattribute)など) が一般的に使用されます。 この例では、属性がクラスに適用される方法を示します。

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>カスタム属性

カスタム属性も定義できます。 カスタム属性は、次の Windows ランタイム規則に従う必要があります。

- カスタム属性は、パブリック フィールドだけを格納できます。

- カスタム属性フィールドは、属性がクラスに適用されるときに初期化できます。

- フィールドは、次に示すいずれかの型になることができます。

  - int32 (int)

  - uint32 (unsigned int)

  - [bool]

  - Platform::String^

  - Windows::Foundation::HResult

  - Platform::Type^

  - パブリック列挙型クラス (ユーザー定義列挙型を含む)

次の例では、カスタム属性を定義し、使用時に初期化する方法を示します。

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>関連項目

[型システム (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
