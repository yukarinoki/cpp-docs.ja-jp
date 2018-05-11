---
title: Runtimeclassbaset::asiid メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35d218666f785685e95d737574ff44e276ce84b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclassbasetasiid-method"></a>RuntimeClassBaseT::AsIID メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 パラメーターで指定されたインターフェイス ID を実装する型`riid`です。  
  
 `implements`  
 テンプレート パラメーターで指定された型の変数`T`です。  
  
 `riid`  
 取得するインターフェイス ID です。  
  
 `ppvObject`  
 ポインターに-を - インターフェイスへのポインターがパラメーターで指定されたこの操作が成功した場合は、`riid`です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、エラーを説明する HRESULT。  
  
## <a name="remarks"></a>コメント  
 指定したインターフェイス ID へのポインターを取得します  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)