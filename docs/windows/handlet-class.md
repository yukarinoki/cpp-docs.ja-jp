---
title: HandleT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99a596bf1e086ac7b1a1a72c3504ce4f41844ba4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="handlet-class"></a>HandleT クラス
オブジェクトへのハンドルを表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `HandleTraits`  
 インスタンス、 [HandleTraits](../windows/handletraits-structure.md)ハンドルの共通の特性を定義する構造。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Traits`|`HandleTraits` と同義。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[HandleT::HandleT コンストラクター](../windows/handlet-handlet-constructor.md)|HandleT クラスの新しいインスタンスを初期化します。|  
|[HandleT::~HandleT デストラクター](../windows/handlet-tilde-handlet-destructor.md)|HandleT クラスのインスタンスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[HandleT::Attach メソッド](../windows/handlet-attach-method.md)|指定したハンドルを現在の HandleT オブジェクトに関連付けます。|  
|[HandleT::Close メソッド](../windows/handlet-close-method.md)|現在の HandleT オブジェクトを閉じます。|  
|[HandleT::Detach メソッド](../windows/handlet-detach-method.md)|基になるハンドルから現在 HandleT オブジェクトの関連付けを解除します。|  
|[HandleT::Get メソッド](../windows/handlet-get-method.md)|基になるハンドルの値を取得します。|  
|[HandleT::IsValid メソッド](../windows/handlet-isvalid-method.md)|現在の HandleT オブジェクトがハンドルを表すかどうかを示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[HandleT::InternalClose メソッド](../windows/handlet-internalclose-method.md)|現在の HandleT オブジェクトを閉じます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[HandleT::operator= 演算子](../windows/handlet-operator-assign-operator.md)|指定した HandleT オブジェクトの値を現在 HandleT オブジェクトに移動します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[HandleT::handle_ データ メンバー](../windows/handlet-handle-data-member.md)|HandleT オブジェクトによって表されるハンドルが含まれています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `HandleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)