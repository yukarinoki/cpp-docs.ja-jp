---
title: Crowset::update |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b40486db73d3d545a3226e71a19ba0b588f631ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetupdate"></a>CRowset::Update
保留中の最後のフェッチ、現在の行に加えられた変更を送信または**更新**それで呼び出します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Update(DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pcRows`  
 [out]場所へのポインターを**更新**しようを更新するために必要な場合の行の数を返します。  
  
 `phRow`  
 [out]場所へのポインターを**更新**を更新しようとしましたが、行のハンドルを返します。 場合はハンドルが返されない`phRow`が null です。  
  
 `pStatus`  
 [out]場所へのポインターを**更新**行の状態値を返します。 場合のステータスが返されない`pStatus`が null です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 保留中の行が最後にフェッチまたは更新された後、現在の行に加えられた変更を送信 (を使用して**更新**または[UpdateAll](../../data/oledb/crowset-updateall.md))。 通常[SetData](../../data/oledb/crowset-setdata.md) 、行内の列のデータ値を設定し、呼び出す**更新**をそれらの変更を転送します。  
  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetUpdate`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetUpdate**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)