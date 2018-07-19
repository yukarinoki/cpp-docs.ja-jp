---
title: IPersistStorageImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
dev_langs:
- C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634a7a7373f6686ad36b645a73613a4ae350bbab
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884702"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl クラス
このクラスは、実装、 [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731)インターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IPersistStorageImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|オブジェクトのすべてのストレージ オブジェクトを解放し、HandsOff モードに入るように指示します。 ATL の実装では、S_OK を返します。|  
|[IPersistStorageImpl::InitNew](#initnew)|新しい記憶域を初期化します。|  
|[IPersistStorageImpl::IsDirty](#isdirty)|最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStorageImpl::Load](#load)|指定された記憶域からオブジェクトのプロパティを読み込みます。|  
|[IPersistStorageImpl::Save](#save)|オブジェクトのプロパティを指定したストレージに保存します。|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|そのストレージ オブジェクトへの書き込みを通常モードに戻ることができますをオブジェクトに通知します。 ATL の実装では、S_OK を返します。|  
  
## <a name="remarks"></a>Remarks  
 `IPersistStorageImpl` 実装して、 [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731)インターフェイス、オブジェクトの読み込みを要求するクライアントのできるし、ストレージを使用して、永続的なデータを保存します。  
  
 このクラスの実装には、クラスが必要です。`T`の実装を、`IPersistStreamInit`インターフェイスを介して使用できる`QueryInterface`します。 通常これはそのクラス`T`から派生する必要があります[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)、エントリを提供`IPersistStreamInit`で、 [COM マップ](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)を使用して、[プロパティ マップ](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427)クラスの永続的なデータを記述します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK にします。  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 オブジェクトのすべてのストレージ オブジェクトを解放し、HandsOff モードに入るように指示します。  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) Windows SDK にします。  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 新しい記憶域を初期化します。  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Remarks  
 ATL の実装のデリゲートを[IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイス。  
  
 参照してください[IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) Windows SDK にします。  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Remarks  
 ATL の実装のデリゲートを[IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイス。  
  
 参照してください[IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) Windows SDK にします。  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 指定された記憶域からオブジェクトのプロパティを読み込みます。  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Remarks  
 ATL の実装のデリゲートを[IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイス。 `Load` 「コンテンツ」という名前のストリームを使用して、オブジェクトのデータを取得します。 [保存](#save)メソッドが最初にこのストリームを作成します。  
  
 参照してください[IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) Windows SDK にします。  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 オブジェクトのプロパティを指定したストレージに保存します。  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Remarks  
 ATL の実装のデリゲートを[IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイス。 ときに`Save`最初が呼び出されると、指定された記憶域に「コンテンツ」をという名前のストリームを作成します。 このストリームは以降の呼び出しで使用し、`Save`と呼び出し[ロード](#load)します。  
  
 参照してください[IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) Windows SDK にします。  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 そのストレージ オブジェクトへの書き込みを通常モードに戻ることができますをオブジェクトに通知します。  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [記憶域とストリーム](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl クラス](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl クラス](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
