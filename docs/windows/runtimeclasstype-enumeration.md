---
title: RuntimeClassType 列挙型 |Microsoft Docs
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
ms.openlocfilehash: 1b54813a41a8857e4533f21d1eb0adaf8dcecd25
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010822"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 列挙型
型を指定[RuntimeClass](../windows/runtimeclass-class.md)サポートされているインスタンス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ClassicCom`|クラシック COM ランタイム クラスです。|  
|`Delegate`|これは、`ClassicCom` に相当します。|  
|`InhibitFtmBase`|無効にします`FtmBase`する際にサポート`__WRL_CONFIGURATION_LEGACY__`が定義されていません。|  
|`InhibitWeakReference`|弱い参照のサポートを無効にします。|  
|`WinRt`|Windows ランタイム クラスです。|  
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)