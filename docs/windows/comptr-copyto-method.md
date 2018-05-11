---
title: Comptr::copyto メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 680c1278ca2b17c7ea35e72946fb5d5030c5e7c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo メソッド
指すポインターを指定するには、この ComPtr に関連付けられている現在または指定されたインターフェイスをコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  

template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 型の名前。  
  
 `ptr`  
 この操作の完了時、要求されたインターフェイスへのポインター。  
  
 `riid`  
 インターフェイス ID。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、暗黙の QueryInterface 操作が失敗した理由を示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 最初の関数は、この ComPtr に関連付けられたインターフェイスへのポインターのコピーを返します。 この関数は、常に S_OK を返します。  
  
 2 番目の関数で指定されたインターフェイスのこの ComPtr に関連付けられているインターフェイスの QueryInterface 演算を実行する、`riid`パラメーター。  
  
 3 番目の関数のインターフェイスの基になるため、この ComPtr に関連付けられているインターフェイスの QueryInterface 演算を実行する、`U`パラメーター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)