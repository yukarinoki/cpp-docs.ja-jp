---
title: エクスポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 48c4a645456e3b3c0556dfed268ce911e5799fc3
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569418"
---
# <a name="export"></a>export
.Idl ファイルに配置するデータ構造をによりします。  
  
## <a name="syntax"></a>構文  
  
```  
[export]  
```  
  
## <a name="remarks"></a>Remarks  
 **エクスポート**C++ 属性は、.idl ファイルに配置して、ある使用可能な任意の言語で使用できるようにするバイナリ互換性のある形式で、タイプ ライブラリ内のデータ構造をによりします。  
  
 適用することはできません、**エクスポート**クラスでは、パブリック メンバーのみが持つ場合でも、属性をクラス (と同等の**構造体**)。  
  
 名前のないをエクスポートする場合**enum**s または**構造体**s で始まる指定した名前になる **_ _unnamed * * * x*ここで、 *x*シーケンシャル数です。  
  
 エクスポートの有効な typedef は、基本型、構造体、共用体、列挙型はか、識別子を入力します。  参照してください[typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287)詳細についてはします。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、**エクスポート**属性。  
  
```cpp  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**共用体**、 **typedef**、 **enum**、**構造体**、または**インターフェイス**|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   