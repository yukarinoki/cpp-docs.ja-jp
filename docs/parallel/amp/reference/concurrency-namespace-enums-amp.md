---
title: Concurrency 名前空間の列挙型 (AMP) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a67b5e77b8ab8c52e55dea96e64a3f16a4d70e39
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695669"
---
# <a name="concurrency-namespace-enums-amp"></a>Concurrency 名前空間の列挙型 (AMP)
|||  
|-|-|  
|[access_type 列挙型](#access_type)|[queuing_mode 列挙型](#queuing_mode)|  
  
##  <a name="access_type"></a>  access_type 列挙型  
 データへのさまざまな種類のアクセスを示すために使用される列挙型。  
  
```  
enum access_type;  
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`access_type_auto`|アクセラレータに最も適した `access_type` を自動的に選択します。|  
|`access_type_none`|専用。 割り当ては、アクセラレータ上でのみアクセスでき、CPU 上ではアクセスできません。|  
|`access_type_read`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では読み取り可能です。|  
|`access_type_read_write`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では書き込み可能です。|  
|`access_type_write`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では読み取りおよび書き込みの両方ができます。|  

  
##  <a name="queuing_mode"></a>  queuing_mode 列挙型  
 アクセラレータでサポートされているキュー モードを指定します。  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`queuing_mode_immediate`|キュー モードを指定するコマンドなど、 [parallel_for_each 関数 (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)、呼び出し元に返されるとすぐに、対応するアクセラレータ デバイスに送信されます。|  
|`queuing_mode_automatic`|キュー モードに対応するコマンド キューに入れするコマンドを指定する、 [accelerator_view](accelerator-view-class.md)オブジェクト。 コマンドは、デバイスに送信されるときに[accelerator_view::flush](accelerator-view-class.md#flush)と呼びます。|   
  
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
