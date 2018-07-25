---
title: CreatorMap 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: a6113737d7463354ffa273ced61b190246f63a83
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873285"
---
# <a name="creatormap-structure"></a>CreatorMap 構造体
Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>コメント  
 初期化、登録、およびオブジェクトの登録を解除する方法についてを説明します。  
  
 CreatorMap には、次の情報が含まれています。  
  
-   初期化、登録、およびオブジェクトの登録を解除する方法。  
  
-   従来の COM または Windows ランタイム ファクトリによってライセンス認証データを比較する方法。  
  
-   インターフェイスのファクトリ キャッシュおよびサーバー名に関する情報です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CreatorMap::activationId データ メンバー](../windows/creatormap-activationid-data-member.md)|クラシック COM クラス ID または Windows ランタイム名前によって識別されるオブジェクト ID を表します。|  
|[CreatorMap::factoryCache データ メンバー](../windows/creatormap-factorycache-data-member.md)|CreatorMap のファクトリ キャッシュへのポインターを格納します。|  
|[CreatorMap::factoryCreator データ メンバー](../windows/creatormap-factorycreator-data-member.md)|指定した CreatorMap のファクトリを作成します。|  
|[CreatorMap::serverName データ メンバー](../windows/creatormap-servername-data-member.md)|CreatorMap のサーバー名を格納します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CreatorMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)