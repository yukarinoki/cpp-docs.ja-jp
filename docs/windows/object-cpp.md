---
title: オブジェクト (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 601d67fb48f0ae826474d33e7dca0fbffff9478c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="object-c"></a>object (C++)
カスタムのインターフェイスを識別します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>コメント  
 インターフェイス定義の直前、**オブジェクト**C++ 属性により、インターフェイス、カスタム インターフェイスとして .idl ファイル内に配置されます。  
  
 オブジェクトでマークされた任意のインターフェイスを継承する必要があります**IUnknown**です。 継承の基本インターフェイスのいずれかの場合、この条件が満たされる**IUnknown**です。 基本インターフェイスを継承できない場合**IUnknown**、コンパイラでマークされたインターフェイスと、**オブジェクト**から派生する**IUnknown**です。  
  
## <a name="example"></a>例  
 参照してください[nonbrowsable](../windows/nonbrowsable.md)の使用方法の例については**オブジェクト**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [デュアル](../windows/dual.md)   
 [ディスパッチ インターフェイス](../windows/dispinterface.md)   
 [ユーザー設定](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
