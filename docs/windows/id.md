---
title: id |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c674765a0dfc06648d64a2b3b4e820bb467e700
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882448"
---
# <a name="id"></a>ID
指定します、 `dispid` (プロパティまたはメソッド、インターフェイスまたはディスパッチ インターフェイス) のメンバー関数のパラメーターです。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dispid`  
 インターフェイス メソッドのディスパッチ ID。  
  
## <a name="remarks"></a>コメント  
 **Id** C++ 属性と同じ機能を持つ、 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[バインド可能な](../windows/bindable.md)の使用方法の例については**id**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [データ メンバー属性](../windows/data-member-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [in](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   
