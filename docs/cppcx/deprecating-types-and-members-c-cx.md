---
title: 型およびメンバーの非推奨化 (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 7f488dfa522c0b48c75150d40584b0946baae806
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301501"
---
# <a name="deprecating-types-and-members-ccx"></a>型およびメンバーの非推奨化 (C++/CX)

C++/cli CX、プロデューサーおよびコンシューマーを使用して用の Windows ランタイム型とメンバーの非推奨となる、[非推奨](/uwp/api/windows.foundation.metadata.deprecatedattribute)属性はサポートされています。 この属性が適用された API を利用すると、その API は非推奨とされており、代替 API の使用を推奨する警告メッセージがコンパイル時に表示されます。 独自のパブリック型およびメソッドでこの属性を適用し、独自のカスタム メッセージを提供することもできます。

> [!CAUTION]
> [Deprecated](/uwp/api/windows.foundation.metadata.deprecatedattribute)属性は Windows ランタイム型でのみ使用されます。 標準 C++ のクラスおよびメンバーの場合は、 [__declspec(deprecated)](../cpp/deprecated-cpp.md)を使用します。

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

| |
|-|
|XAML コントロール|
|delegate|
|event|
|列挙型フィールド|
|enum|
|struct|
|メソッド|
|class|
|interface|
|property|
|構造体のフィールド|
|パラメーター化されたコンストラクター|

## <a name="see-also"></a>関連項目

[型システム](../cppcx/type-system-c-cx.md)<br/>
[Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間参照](../cppcx/namespaces-reference-c-cx.md)
