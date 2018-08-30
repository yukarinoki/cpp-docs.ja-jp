---
title: ISupportErrorInfoImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa9ee25403464a13418081abc8e8e150c7e03500
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217460"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl クラス
このクラスの既定の実装を提供する、 [ISupportErrorInfo インターフェイス](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo)1 つのインターフェイスのみがオブジェクトのエラーを生成するときに使用できます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>パラメーター  
 *piid*  
 サポートするインターフェイスの IID へのポインター [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|インターフェイスがで識別されるかどうかを示す`riid`サポート、 [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)インターフェイス。|  
  
## <a name="remarks"></a>Remarks  
 [ISupportErrorInfo インターフェイス](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo)により、クライアントにエラー情報を返されることができます。 使用するオブジェクト`IErrorInfo`実装する必要があります`ISupportErrorInfo`します。  
  
 クラス`ISupportErrorInfoImpl`の既定の実装を提供します。 `ISupportErrorInfo` 、1 つのインターフェイスのみがオブジェクトのエラーを生成するときに使用できます。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 インターフェイスがで識別されるかどうかを示す`riid`サポート、 [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)インターフェイス。  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[ISupportErrorInfo::InterfaceSupportsErrorInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) Windows SDK にします。  
  
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
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
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
  
 場合*nNumThreads*ゼロ、 [ATLS_DEFAULT_THREADSPERPROC](https://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571)スレッドの合計数を取得するマシンのプロセッサ数が乗算されます。  
  
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
 [クラスの概要](../../atl/atl-class-overview.md)
