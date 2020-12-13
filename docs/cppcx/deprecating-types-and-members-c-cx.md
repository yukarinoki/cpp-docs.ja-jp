---
description: 詳細については、「非推奨 types and members (C++/CX)」を参照してください。
title: 型およびメンバーの非推奨化 (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: fddb9ecd81045655f3ca80c41e0fa3103d3ff52d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341998"
---
# <a name="deprecating-types-and-members-ccx"></a>型およびメンバーの非推奨化 (C++/CX)

C++/CX では、 [非推奨](/uwp/api/windows.foundation.metadata.deprecatedattribute) の属性を使用して、プロデューサーとコンシューマーの Windows ランタイム型およびメンバーの非推奨がサポートされています。 この属性が適用された API を利用すると、その API は非推奨とされており、代替 API の使用を推奨する警告メッセージがコンパイル時に表示されます。 独自のパブリック型およびメソッドでこの属性を適用し、独自のカスタム メッセージを提供することもできます。

> [!CAUTION]
> [非推奨](/uwp/api/windows.foundation.metadata.deprecatedattribute)の属性は Windows ランタイム型でのみ使用されます。 標準 C++ のクラスおよびメンバーの場合は、 [__declspec(deprecated)](../cpp/deprecated-cpp.md)を使用します。

### <a name="example"></a>例

次の例では、たとえば Windows ランタイム コンポーネントで、独自のパブリック API を非推奨にする方法を示します。 型 [Windows:Foundation::Metadata::DeprecationType](/uwp/api/windows.foundation.metadata.deprecationtype) 型の 2 番目のパラメーターは、API が非推奨であるか、削除済みであるかを指定します。 現在 DeprecationType::Deprecated という値のみがサポートされています。 属性の 3 番目のパラメーターは、属性の適用対象である [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) を指定します。

```

namespace wfm = Windows::Foundation::Metadata;

public ref class Bicycle sealed
{

public:
    property double Speed;

    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]
    double ComputeAngularVelocity();
};
```

## <a name="supported-targets"></a>サポート対象

次の表では、非推奨の属性を適用できるコンストラクトを示します:

:::row:::
   :::column span="":::
      講義
      人
      enum
      列挙型フィールド \
      場合
      interface
   :::column-end:::
   :::column span="":::
      b
      パラメーター化されたコンストラクター \
      プロパティ\
      体型
      構造体フィールド \
      XAML コントロール
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>関連項目

[型システム](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
