---
title: 属性 (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 491b3cabd8003664a34543d8bb7a640759bd50ee
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207406"
---
# <a name="attributes-ccx"></a>属性 (C++/CX)
属性は、メタデータ作成で特定の動作を指定するには、Windows ランタイム型とメソッドの角かっこの前に付加する ref クラスの特殊なです。 複数の属性の定義済み — たとえば、 [Windows::Foundation::Metadata::WebHostHidden](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)-C + でよく使用される/cli/CX コード。 この例では、属性がクラスに適用される方法を示します。  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>カスタム属性  
 カスタム属性も定義できます。 カスタム属性は、Windows ランタイムのこれらの規則に従う必要があります。  
  
-   カスタム属性は、パブリック フィールドだけを格納できます。  
  
-   カスタム属性フィールドは、属性がクラスに適用されるときに初期化できます。  
  
-   フィールドは、次に示すいずれかの型になることができます。  
  
    -   int32 (int)  
  
    -   uint32 (unsigned int)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   パブリック列挙型クラス (ユーザー定義列挙型を含む)  
  
 次の例では、カスタム属性を定義し、使用時に初期化する方法を示します。  
  
 [!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]  
  
## <a name="see-also"></a>関連項目  
 [型システム (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)