---
title: Irowsetnotifyimpl::onrowchange |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
dev_langs:
- C++
helpviewer_keywords:
- OnRowChange method
ms.assetid: 148bee03-3707-4bbf-8c51-657efc63645f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8eae9d40b34adb6368b863f3534c5867a90979af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105609"
---
# <a name="irowsetnotifyimplonrowchange"></a>IRowsetNotifyImpl::OnRowChange
行に対する最初の変更や行全体に影響する変更のコンシューマーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms722694.aspx)パラメーターの説明をします。  
  
## <a name="return-value"></a>戻り値  
 参照してください[は、](https://msdn.microsoft.com/en-us/library/ms722694.aspx)戻り値についてです。  
  
## <a name="remarks"></a>コメント  
 このメソッドをラップ、[は、](https://msdn.microsoft.com/en-us/library/ms722694.aspx)メソッドです。 詳細については、OLE DB プログラマーズ リファレンス内のメソッドの説明を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetNotifyImpl クラス](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx)