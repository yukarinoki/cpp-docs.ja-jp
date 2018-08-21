---
title: helpcontext |Microsoft Docs
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
ms.openlocfilehash: c505d6ebf62e6c01ecd3c2f750cec1c95775f53d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642429"
---
# <a name="helpcontext"></a>helpcontext
ユーザーには、この要素に関する情報を表示できるようにコンテキスト ID を指定します、**ヘルプ**ファイル。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ helpcontext(  
   id  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *ID*  
 ヘルプ トピックのコンテキスト ID。 参照してください[HTML ヘルプ: プログラムの状況依存のヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)コンテキスト Id の詳細についてはします。  
  
## <a name="remarks"></a>Remarks  
 **Helpcontext** C++ 属性と同じ機能を持つ、 [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL 属性。  
  
## <a name="example"></a>例  
 例をご覧ください[defaultvalue](../windows/defaultvalue.md)を使用する方法の例については**helpcontext**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**インターフェイス**、 **typedef**、**クラス**メソッド、プロパティ|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Helpfile](../windows/helpfile.md)   
 [helpstring](../windows/helpstring.md)   