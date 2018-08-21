---
title: エントリ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f644df2969954187aa4506d2cc1d04d140f88de3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642888"
---
# <a name="entry"></a>entry
DLL 内のエントリ ポイントを識別することによって、モジュールで、エクスポートされた関数または定数を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ entry(  
   id  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 エントリ ポイントの ID。  
  
## <a name="remarks"></a>Remarks  
 **エントリ**C++ 属性と同じ機能を持つ、[エントリ](http://msdn.microsoft.com/library/windows/desktop/aa366815)MIDL 属性。  
  
## <a name="example"></a>例  
 例をご覧ください[idl_module](../windows/idl-module.md)の使用例の**エントリ**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`idl_module` 属性|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   