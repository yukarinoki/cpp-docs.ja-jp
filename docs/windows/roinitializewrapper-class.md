---
title: RoInitializeWrapper クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/20/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cac71857e6b472f11d1c9eaba48d181ea78fb456
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705593"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper クラス
Windows ランタイムを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>コメント  
 RoInitializeWrapper は、利便性のための Windows ランタイムを初期化し、操作が成功したかどうかを示す HRESULT を返します。 クラスのデストラクターを呼び出すため`::Windows::Foundation::Uninitialize`のインスタンス`RoInitializeWrapper`グローバルまたは最上位のスコープで宣言する必要があります。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper コンストラクター](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|RoInitializeWrapper クラスの新しいインスタンスを初期化します。|  
|[RoInitializeWrapper::~RoInitializeWrapper デストラクター](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|RoInitializeWrapper クラスの現在のインスタンスを破棄します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT() 演算子](../windows/roinitializewrapper-hresult-parens-operator.md)|RoInitializeWrapper コンス トラクターが生成された HRESULT を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)