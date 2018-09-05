---
title: IThreadPoolConfig インターフェイス |Microsoft Docs
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
ms.openlocfilehash: 5f23e46f2ef8de61e6dccc16a24e8c4bcfaa8f2e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677085"
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
|[GetSize](#getsize)|プールのスレッドの数を取得するには、このメソッドを呼び出します。|  
|[GetTimeout](#gettimeout)|スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。|  
|[SetSize](#setsize)|プールのスレッドの数を設定するには、このメソッドを呼び出します。|  
|[SetTimeout](#settimeout)|スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時間を設定するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスによって実装されます[CThreadPool](../../atl/reference/cthreadpool-class.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="getsize"></a>  IThreadPoolConfig::GetSize  
 プールのスレッドの数を取得するには、このメソッドを呼び出します。  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnNumThreads*  
 [out]成功した場合、プールのスレッドの数を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>  IThreadPoolConfig::GetTimeout  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwMaxWait*  
 [out]成功した場合、スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で時間の最大値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)します。  
  
##  <a name="setsize"></a>  IThreadPoolConfig::SetSize  
 プールのスレッドの数を設定するには、このメソッドを呼び出します。  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 *nNumThreads*  
 要求されたプール内のスレッド数。  
  
 場合*nNumThreads*が負の場合、その絶対値で乗算されますスレッドの合計数を取得するマシンでプロセッサの数。  
  
 場合*nNumThreads*ゼロ、ATLS_DEFAULT_THREADSPERPROC はスレッドの合計数を取得するマシンのプロセッサ数が乗算されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)します。  
  
##  <a name="settimeout"></a>  IThreadPoolConfig::SetTimeout  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時間を設定するには、このメソッドを呼び出します。  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwMaxWait*  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で要求された最大時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)   
 [CThreadPool クラス](../../atl/reference/cthreadpool-class.md)
