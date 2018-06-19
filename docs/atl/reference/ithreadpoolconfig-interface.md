---
title: IThreadPoolConfig インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 237671ce971d54209f3889fd93396fb4e0a42fee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363730"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig インターフェイス
このインターフェイスは、スレッド プールを構成するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetSize](#getsize)|このメソッドを呼び出して、プール内のスレッドの数を取得します。|  
|[GetTimeout](#gettimeout)|このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を取得します。|  
|[SetSize](#setsize)|プールのスレッドの数を設定するには、このメソッドを呼び出します。|  
|[setTimeout](#settimeout)|このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を設定します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスはによって実装[CThreadPool](../../atl/reference/cthreadpool-class.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="getsize"></a>  IThreadPoolConfig::GetSize  
 このメソッドを呼び出して、プール内のスレッドの数を取得します。  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 `pnNumThreads`  
 [out]成功した場合、プール内のスレッドの数を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout  
 このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を取得します。  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>パラメーター  
 `pdwMaxWait`  
 [out]成功した場合、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)です。  
  
##  <a name="setsize"></a>  IThreadPoolConfig::SetSize  
 プールのスレッドの数を設定するには、このメソッドを呼び出します。  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumThreads`  
 プール内のスレッドの要求数。  
  
 場合`nNumThreads`は負の場合、その絶対値を掛けたスレッドの合計数を取得するマシンでプロセッサの数。  
  
 場合`nNumThreads`ゼロ、 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571)スレッドの合計数を取得するマシンのプロセッサ数で乗算されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)です。  
  
##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout  
 このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を設定します。  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMaxWait`  
 スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で要求の最大時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)です。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)   
 [CThreadPool クラス](../../atl/reference/cthreadpool-class.md)
