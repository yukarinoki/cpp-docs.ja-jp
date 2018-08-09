---
title: Comptr::copyto メソッド |Microsoft Docs
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
ms.openlocfilehash: 5b387d52c9ab7b1d9033ce70d36e9f0aa5e5b33e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642930"
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo メソッド
これに関連付けられている現在または指定されたインターフェイスのコピー **ComPtr**へのポインターを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
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
  
### <a name="parameters"></a>パラメーター  
 *U*  
 型の名前。  
  
 *ptr*  
 この操作が完了時は、要求されたインターフェイスへのポインター。  
  
 *riid*  
 インターフェイス ID。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、その理由を示す HRESULT 暗黙`QueryInterface`操作に失敗しました。  
  
## <a name="remarks"></a>Remarks  
 最初の関数は、これに関連付けられているインターフェイスへのポインターのコピーを返します**ComPtr**します。 この関数は、常に S_OK を返します。  
  
 2 番目の関数の実行、`QueryInterface`これに関連付けられているインターフェイスで操作**ComPtr**で指定されたインターフェイスの*riid*パラメーター。  
  
 3 番目の関数の実行、`QueryInterface`これに関連付けられているインターフェイスで操作**ComPtr**の基になるインターフェイスの*U*パラメーター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)