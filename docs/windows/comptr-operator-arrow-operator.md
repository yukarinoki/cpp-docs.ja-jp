---
title: Comptr::operator-&gt;演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3cb3571207f328ad044ffd3f2f9b83bcebc7677e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperator-gt-operator"></a>Comptr::operator-&gt;演算子
現在のテンプレート パラメーターで指定された型へのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>戻り値  
 現在のテンプレート型名で指定された型へのポインター。  
  
## <a name="remarks"></a>コメント  
 このヘルパー関数では、不要なオーバーヘッドが STDMETHOD マクロを使用して原因を削除します。 この関数で IUnknown 型は仮想ではなくプライベートです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)