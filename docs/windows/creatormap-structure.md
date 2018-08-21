---
title: CreatorMap 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 173b41c6d36d36b7d8a0f4e7b024e845eec6ae4a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650506"
---
# <a name="creatormap-structure"></a>CreatorMap 構造体
Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>Remarks  
 初期化し登録、およびオブジェクトの登録を解除する方法についてを説明します。  
  
 **CreatorMap**次の情報が含まれています。  
  
-   初期化し登録、およびオブジェクトの登録を解除する方法。  
  
-   従来の COM または Windows ランタイムのファクトリによってライセンス認証データを比較する方法。  
  
-   インターフェイスのファクトリ キャッシュおよびサーバー名について説明します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CreatorMap::activationId データ メンバー](../windows/creatormap-activationid-data-member.md)|クラシック COM クラスの ID または Windows ランタイムの名前によって識別されるオブジェクト ID を表します。|  
|[CreatorMap::factoryCache データ メンバー](../windows/creatormap-factorycache-data-member.md)|工場出荷時のキャッシュへのポインターを格納、 **CreatorMap**します。|  
|[CreatorMap::factoryCreator データ メンバー](../windows/creatormap-factorycreator-data-member.md)|指定したファクトリを作成します**CreatorMap**します。|  
|[CreatorMap::serverName データ メンバー](../windows/creatormap-servername-data-member.md)|サーバー名を格納、 **CreatorMap**します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CreatorMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)