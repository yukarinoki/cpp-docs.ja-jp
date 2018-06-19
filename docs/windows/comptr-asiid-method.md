---
title: Comptr::asiid メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26f56a9d94620067ae31f5b4984ff24fe703822e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870091"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID メソッド
指定されたインターフェイス ID で識別されるインターフェイスを表す ComPtr オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 インターフェイス ID。  
  
 `p`  
 指定されたインターフェイスへの二重間接ポインター サポートされている場合、`riid`パラメーター、それ以外の IUnknown へのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)