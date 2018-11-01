---
title: テンプレート ref クラス (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: a128b9fcc7b37ad2cf7c7a17abb24c8074952501
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642210"
---
# <a name="template-ref-classes-ccx"></a>テンプレート ref クラス (C++/CX)

C++ テンプレートはメタデータに発行されないため、プログラム内でパブリック アクセシビリティおよび保護されたアクセシビリティを持つことはできません。 もちろん、プログラムで、標準 C++ テンプレートを内部的に使用できます。 さらに、パブリック ref クラスをテンプレートとして定義し、明示的に特化したテンプレート ref クラスをプライベート ref クラスのプライベート メンバーとして宣言できます。

## <a name="authoring-ref-class-templates"></a>ref クラス テンプレートの作成

次の例は、プライベート ref クラスをテンプレートとして宣言する方法だけでなく、標準 C++ テンプレートを宣言し、それら両方をパブリック ref クラスのメンバーとして宣言する方法も示します。 これで、Windows ランタイムの種類によって、標準 C++ テンプレートを特化できることに注意してください場合は、platform::string ^ です。

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>関連項目

[型システム (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間参照](../cppcx/namespaces-reference-c-cx.md)