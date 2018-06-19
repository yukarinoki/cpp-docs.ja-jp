---
title: IWorkerThreadClient インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8336edb07d02bbbcd5775eaf3ef8fe0f735d3adb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359818"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient インターフェイス
`IWorkerThreadClient` クライアントによって実装されるインターフェイスは、[使用](../../atl/reference/cworkerthread-class.md)クラスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。|  
|[実行します。](#execute)|このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。|  
  
## <a name="remarks"></a>コメント  
 シグナル状態になるハンドルへの応答でワーカー スレッドで実行する必要があるコードがある場合は、このインターフェイスを実装します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>パラメーター  
 *hHandle*  
 終了するハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時にエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡されたハンドルはへの呼び出しによって、このオブジェクトに以前関連付けられていた[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
### <a name="example"></a>例  
 次のコードは、の簡単な実装を示しています。`IWorkerThreadClient::CloseHandle`です。  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwParam`  
 ユーザーのパラメーターです。  
  
 `hObject`  
 シグナル状態になるハンドルです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時にエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡される DWORD/ポインター、ハンドルされたへの呼び出しでこのオブジェクトに既に関連付け[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
### <a name="example"></a>例  
 次のコードは、の簡単な実装を示しています。`IWorkerThreadClient::Execute`です。  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)   
 [CWorkerThread クラス](../../atl/reference/cworkerthread-class.md)
