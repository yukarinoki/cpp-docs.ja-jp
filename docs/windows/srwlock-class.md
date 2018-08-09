---
title: SRWLock クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs:
- C++
helpviewer_keywords:
- SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23881f2065276aa7ae7b6ee95b5449abb07dd2de
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641954"
---
# <a name="srwlock-class"></a>SRWLock クラス
スリム リーダー/ライター ロックを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class SRWLock;  
```  
  
## <a name="remarks"></a>Remarks  
 スリム リーダー/ライター ロックは、オブジェクトやリソースをスレッド間でのアクセスを同期に使用されます。 詳細については、次を参照してください。[同期関数](http://msdn.microsoft.com/9b6359c2-0113-49b6-83d0-316ad95aba1b)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|||  
|-|-|  
|`SyncLockExclusive`|シノニム、 **SRWLock**排他モードで取得したオブジェクト。|  
|`SyncLockShared`|シノニム、 **SRWLock**共有モードで取得したオブジェクト。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLock::SRWLock コンストラクター](../windows/srwlock-srwlock-constructor.md)|新しいインスタンスを初期化、 **SRWLock**クラス。|  
|[SRWLock::~SRWLock デストラクター](../windows/srwlock-tilde-srwlock-destructor.md)|インスタンスを初期化解除、 **SRWLock**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLock::LockExclusive メソッド](../windows/srwlock-lockexclusive-method.md)|取得、 **SRWLock**排他モードでのオブジェクト。|  
|[SRWLock::LockShared メソッド](../windows/srwlock-lockshared-method.md)|取得、 **SRWLock**共有モードでのオブジェクト。|  
|[SRWLock::TryLockExclusive メソッド](../windows/srwlock-trylockexclusive-method.md)|取得を試みる、 **SRWLock**オブジェクトの現在または指定された排他モードで**SRWLock**オブジェクト。|  
|[SRWLock::TryLockShared メソッド](../windows/srwlock-trylockshared-method.md)|取得を試みる、 **SRWLock**オブジェクトの現在または指定した共有モードで**SRWLock**オブジェクト。|  
  
### <a name="protected-data-member"></a>保護されたデータ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[SRWLock::SRWLock_ データ メンバー](../windows/srwlock-srwlock-data-member.md)|現在の基になるロック変数が含まれる**SRWLock**オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)