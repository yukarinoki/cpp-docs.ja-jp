---
title: IPersistStorageImpl クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 18f03ba235fdfc14dba22f1759240bd5fb72bafd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl クラス
このクラスは、実装、[すること](http://msdn.microsoft.com/library/windows/desktop/ms679731)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPersistStorageImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|オブジェクトのすべての記憶域オブジェクトを解放し、HandsOff モードに入るように指示します。 ATL の実装を返します`S_OK`です。|  
|[IPersistStorageImpl::InitNew](#initnew)|新しい記憶域を初期化します。|  
|[IPersistStorageImpl::IsDirty](#isdirty)|最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStorageImpl::Load](#load)|指定された記憶域からオブジェクトのプロパティを読み込みます。|  
|[IPersistStorageImpl::Save](#save)|オブジェクトのプロパティを指定された記憶域に保存します。|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|そのストレージ オブジェクトへの書き込みを通常モードに戻ることはできますをオブジェクトに通知します。 ATL の実装を返します`S_OK`です。|  
  
## <a name="remarks"></a>コメント  
 `IPersistStorageImpl` 実装する、[すること](http://msdn.microsoft.com/library/windows/desktop/ms679731)インターフェイス、これにより、クライアントは要求をオブジェクトの負荷と記憶域を使用して、永続的なデータを保存します。  
  
 このクラスの実装には、クラスが必要です。`T`の実装する、`IPersistStreamInit`インターフェイスを介して使用できる`QueryInterface`です。 つまり、通常そのクラス`T`から派生する必要があります[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)のエントリを提供`IPersistStreamInit`で、 [COM マップ](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)、使用して、 [のプロパティマップ](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427)クラスの永続的なデータを記述します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK にします。  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 オブジェクトのすべての記憶域オブジェクトを解放し、HandsOff モードに入るように指示します。  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) Windows SDK にします。  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 新しい記憶域を初期化します。  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>コメント  
 ATL の実装を委任する場合、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。  
  
 参照してください[IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) Windows SDK にします。  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>コメント  
 ATL の実装を委任する場合、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。  
  
 参照してください[IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) Windows SDK にします。  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 指定された記憶域からオブジェクトのプロパティを読み込みます。  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>コメント  
 ATL の実装を委任する場合、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。 **ロード**「コンテンツ」という名前のストリームを使用して、オブジェクトのデータを取得します。 [保存](#save)メソッドが最初にこのストリームを作成します。  
  
 参照してください[IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) Windows SDK にします。  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 オブジェクトのプロパティを指定された記憶域に保存します。  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>コメント  
 ATL の実装を委任する場合、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。 ときに**保存**最初は、呼び出されると、指定された記憶域の「コンテンツ」をという名前のストリームを作成します。 以降の呼び出しでこのストリームを使用して**保存**と呼び出し[ロード](#load)です。  
  
 参照してください[IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) Windows SDK にします。  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 そのストレージ オブジェクトへの書き込みを通常モードに戻ることはできますをオブジェクトに通知します。  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [記憶域とストリーム](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl クラス](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl クラス](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
