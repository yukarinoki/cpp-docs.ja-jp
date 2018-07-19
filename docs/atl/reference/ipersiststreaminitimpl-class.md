---
title: IPersistStreamInitImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b862d6b0fc99184232621432ec1c2a1027f8a9d5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881504"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl クラス
このクラスは実装`IUnknown`の既定の実装を提供し、 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IPersistStreamInitImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|オブジェクトのデータを保存するために必要なストリームのサイズを取得します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IPersistStreamInitImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。|  
|[IPersistStreamInitImpl::IsDirty](#isdirty)|最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStreamInitImpl::Load](#load)|指定したストリームからオブジェクトのプロパティを読み込みます。|  
|[IPersistStreamInitImpl::Save](#save)|オブジェクトのプロパティを指定したストリームに保存します。|  
  
## <a name="remarks"></a>Remarks  
 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスにより、クライアントは、オブジェクトは読み込みし、その永続的なデータを 1 つのストリームに保存を要求します。 クラス`IPersistStreamInitImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK にします。  
  
##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax  
 オブジェクトのデータを保存するために必要なストリームのサイズを取得します。  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287) Windows SDK にします。  
  
##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew  
 新しく作成されたオブジェクトを初期化します。  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234) Windows SDK にします。  
  
##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty  
 最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092) Windows SDK にします。  
  
##  <a name="load"></a>  IPersistStreamInitImpl::Load  
 指定したストリームからオブジェクトのプロパティを読み込みます。  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>Remarks  
 ATL では、オブジェクトのプロパティのマップを使用して、この情報を取得します。  
  
 参照してください[IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) Windows SDK にします。  
  
##  <a name="save"></a>  IPersistStreamInitImpl::Save  
 オブジェクトのプロパティを指定したストリームに保存します。  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>Remarks  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を格納します。  
  
 参照してください[IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [記憶域とストリーム](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [クラスの概要](../../atl/atl-class-overview.md)
