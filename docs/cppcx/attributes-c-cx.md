---
title: 属性 (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 627e89c844b97637897c9b5eb6c1cc7e32081fd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="attributes-ccx"></a>属性 (C++/CX)
属性は、メタデータ作成で特定の動作を指定するには、Windows ランタイム型とメソッドに角かっこの前に付加する ref クラスの特殊なです。 複数の定義済み属性 — たとえば、 [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— C + でよく使用される +/CX コード。 この例では、属性がクラスに適用される方法を示します。  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>カスタム属性  
 カスタム属性も定義できます。 カスタム属性は、以下の Windows ランタイムの規則に従う必要があります。  
  
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