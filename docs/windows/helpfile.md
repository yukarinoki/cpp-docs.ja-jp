---
title: helpfile |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 926d0fec27bf323f559ad2fe0dffbd4208b1bf2a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="helpfile"></a>helpfile
タイプ ライブラリのヘルプ ファイルの名前を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ helpfile(  
   "filename"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ファイル名*  
 ヘルプ トピックが含まれているファイルの名前。  
  
## <a name="remarks"></a>コメント  
 **Helpfile** C++ 属性と同じ機能を持つ、 [helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[モジュール](../windows/module-cpp.md)の使用方法の例については**helpfile**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`、 `typedef`、**クラス**、メソッド、プロパティ|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
