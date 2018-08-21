---
title: Deferrableeventargs::getdeferral メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38958be32b03d0fe4a65a0dfe732d4a15c4ce633
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645085"
---
# <a name="deferrableeventargsgetdeferral-method"></a>DeferrableEventArgs::GetDeferral メソッド
参照を取得、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)遅延イベントを表すオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
### <a name="parameters"></a>パラメーター  
 *結果*  
 参照するポインター、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)呼び出しの完了時のオブジェクトします。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>Remarks  
 コード例では、次を参照してください。 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)