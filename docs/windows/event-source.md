---
title: event_source |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_source
dev_langs:
- C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7e7e287d68bac0fe69417fe21df27ed3231cce6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="eventsource"></a>event_source
イベント ソースを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ event_source(  
   type,  
   optimize=[speed | size],  
   decorate=[true | false]  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 次の値のいずれかの列挙です。  
  
-   アンマネージ C/C++ コード用の`native` (アンマネージ クラスの既定)。  
  
-   COM コード用の`com` 。 使用する必要があります`coclass`とき`type` =`com`です。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 `type` が **native**の場合、 **optimize=size**と指定すると、クラスのすべてのイベント用に記憶域が (最低) 4 バイトあることを指定でき、(既定の) **optimize=speed** を指定すると、記憶域が 4 * (イベントの #) バイトあることを指定できます。  
  
 **decorate**  
 `type` が **native**の場合、 **decorate=false**と指定すると、結合 (.mrg) ファイル内の拡張名に括弧で囲んでいるクラス名を含まないように指定できます。 [/Fx](../build/reference/fx-merge-injected-code.md) では、.mrg ファイルを生成できます。 既定の**decorate=false**では、結合されたファイルで型名は完全修飾されます。  
  
## <a name="remarks"></a>コメント  
 **event_source** C++ 属性では、それが適用されているクラスまたは構造がイベント ソースとなることを指定します。  
  
 **event_source** は、 [event_receiver](../windows/event-receiver.md) 属性と [__event](../cpp/event.md) キーワードと共に使用します。 イベント レシーバーの作成には、 **event_receiver** を使用します。 イベント ソース内のメソッドで `__event` を使用すると、それらのメソッドをイベントとして指定することができます。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**type** = `type`=**com**|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [_ _event](../cpp/event.md)   
 [_ _hook します。](../cpp/hook.md)   
 [_ _unhook](../cpp/unhook.md)   
 [クラス属性](../windows/class-attributes.md)   
