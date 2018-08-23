---
title: テンプレート ref クラス (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb322ae641a1821ed8434e0ea197acf752698e6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592621"
---
# <a name="template-ref-classes-ccx"></a>テンプレート ref クラス (C++/CX)
C++ テンプレートはメタデータに発行されないため、プログラム内でパブリック アクセシビリティおよび保護されたアクセシビリティを持つことはできません。 もちろん、プログラムで、標準 C++ テンプレートを内部的に使用できます。 さらに、パブリック ref クラスをテンプレートとして定義し、明示的に特化したテンプレート ref クラスをプライベート ref クラスのプライベート メンバーとして宣言できます。  
  
## <a name="authoring-ref-class-templates"></a>ref クラス テンプレートの作成  
 次の例は、プライベート ref クラスをテンプレートとして宣言する方法だけでなく、標準 C++ テンプレートを宣言し、それら両方をパブリック ref クラスのメンバーとして宣言する方法も示します。 これで、Windows ランタイムの種類によって、標準 C++ テンプレートを特化できることに注意してください場合は、platform::string ^ です。  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>関連項目  
 [型システム (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)