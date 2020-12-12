---
description: '詳細情報: テンプレート ref クラス (C++/CX)'
title: テンプレート ref クラス (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: c8f3e668dddd80a2ce05f10f9a5d2ada30096c3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307627"
---
# <a name="template-ref-classes-ccx"></a>テンプレート ref クラス (C++/CX)

C++ テンプレートはメタデータに発行されないため、プログラム内でパブリック アクセシビリティおよび保護されたアクセシビリティを持つことはできません。 もちろん、プログラムで、標準 C++ テンプレートを内部的に使用できます。 さらに、パブリック ref クラスをテンプレートとして定義し、明示的に特化したテンプレート ref クラスをプライベート ref クラスのプライベート メンバーとして宣言できます。

## <a name="authoring-ref-class-templates"></a>ref クラス テンプレートの作成

次の例は、プライベート ref クラスをテンプレートとして宣言する方法だけでなく、標準 C++ テンプレートを宣言し、それら両方をパブリック ref クラスのメンバーとして宣言する方法も示します。 標準 C++ テンプレートは、Windows ランタイム型 (この場合は Platform:: String ^) によって特殊化されていることに注意してください。

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>関連項目

[型システム (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
