---
title: WeakReference Class1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a44b992138371ff33a9059990a5ec3e93689c679
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891647"
---
# <a name="weakreference-class1"></a>WeakReference Class1
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class WeakReference;  
```  
  
## <a name="remarks"></a>コメント  
 表す、*弱い参照*Windows ランタイムまたはクラシック COM で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。  
  
 A`WeakReference`オブジェクトを保持、*強い参照*、オブジェクトへのポインターであると*強力な参照カウント*、これは、強い参照によって配布されているコピー数Resolve() メソッド。 強力な参照カウントが 0 でないときに、強力な参照が無効にされ、そのオブジェクトはアクセスできます。 強力な参照カウントには、ゼロになると、強力な参照が無効とオブジェクトにアクセスできません。  
  
 WeakReference オブジェクトは通常、外部スレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すため使用されます。 たとえば、ファイル オブジェクトへの参照から WeakReference オブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。  
  
 WeakReference メソッドでは、スレッド セーフです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[WeakReference::WeakReference コンストラクター](../windows/weakreference-weakreference-constructor.md)|WeakReference クラスの新しいインスタンスを初期化します。|  
|[WeakReference::~WeakReference デストラクター](../windows/weakreference-tilde-weakreference-destructor.md)|初期化を解除 (破棄)、WeakReference クラスの現在のインスタンス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[WeakReference::DecrementStrongReference メソッド](../windows/weakreference-decrementstrongreference-method.md)|現在の WeakReference オブジェクトの厳密な参照カウントをデクリメントします。|  
|[WeakReference::IncrementStrongReference メソッド](../windows/weakreference-incrementstrongreference-method.md)|現在の WeakReference オブジェクトの厳密な参照カウントをインクリメントします。|  
|[WeakReference::Resolve メソッド](../windows/weakreference-resolve-method.md)|強力な参照カウントが 0 以外の場合は、現在の強い参照値に指定されたポインターを設定します。|  
|[WeakReference::SetUnknown メソッド](../windows/weakreference-setunknown-method.md)|指定されたインターフェイス ポインターを現在の WeakReference オブジェクトの強い参照を設定します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `WeakReference`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)