---
title: retval |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6f17f44e520018f82dc82abe88427a2410d68e7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606352"
---
# <a name="retval"></a>retval
メンバーの戻り値を受け取るパラメーターを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
[retval]  
```  
  
## <a name="remarks"></a>Remarks  
 **Retval** C++ 属性と同じ機能を持つ、 [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL 属性。  
  
 **retval**関数の宣言の最後の引数に表示する必要があります。  
  
## <a name="example"></a>例  
 例をご覧ください[バインド可能な](../windows/bindable.md)の使用サンプル**retval**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイスのパラメーター、インターフェイス メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|**out**|  
|**無効な属性**|**in**|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [メソッド属性](../windows/method-attributes.md)   