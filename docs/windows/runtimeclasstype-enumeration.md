---
title: RuntimeClassType 列挙型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43ab0a738af4c6bc92d42c0884827b574946d2ea
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892404"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 列挙型
型を指定[RuntimeClass](../windows/runtimeclass-class.md)サポートされているインスタンス。  
  
## <a name="syntax"></a>構文  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ClassicCom`|クラシック COM ランタイム クラスです。|  
|`Delegate`|等価**ClassicCom**です。|  
|`InhibitFtmBase`|無効に`FtmBase`中にサポート`__WRL_CONFIGURATION_LEGACY__`が定義されていません。|  
|`InhibitWeakReference`|弱い参照のサポートを無効にします。|  
|`WinRt`|Windows ランタイム クラスです。|  
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)