---
title: helpcontext |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 317e204c7292c4a7cccb1f81f6bc9d2a2fbfd407
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877216"
---
# <a name="helpcontext"></a>helpcontext
コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイル内のこの要素を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ helpcontext(  
   id  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `id`  
 ヘルプ トピックのコンテキスト ID です。 参照してください[HTML ヘルプ: プログラムの状況依存のヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)コンテキスト Id の詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 **Helpcontext** C++ 属性と同じ機能を持つ、 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[defaultvalue](../windows/defaultvalue.md)の使用方法の例については**helpcontext**です。  
  
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
 [ヘルプ ファイル](../windows/helpfile.md)   
 [helpstring](../windows/helpstring.md)   
