---
title: IPersistStreamInitImpl クラス |Microsoft ドキュメント
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
ms.openlocfilehash: a51dd5e198a86b7bb17a6182c1edb098f23a8e47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360457"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPersistStreamInitImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|  
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|オブジェクトのデータを保存するために必要なストリームのサイズを取得します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IPersistStreamInitImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。|  
|[IPersistStreamInitImpl::IsDirty](#isdirty)|最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStreamInitImpl::Load](#load)|オブジェクトのプロパティを指定したストリームから読み込みます。|  
|[IPersistStreamInitImpl::Save](#save)|オブジェクトのプロパティを指定したストリームに保存します。|  
  
## <a name="remarks"></a>コメント  
 [Ipersiststreaminit など](http://msdn.microsoft.com/library/windows/desktop/ms682273)インターフェイスを使用して要求するオブジェクトを読み込みますを 1 つのストリームに永続的なデータを保存するクライアント。 クラス`IPersistStreamInitImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID  
 オブジェクトの CLSID を取得します。  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK にします。  
  
##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax  
 オブジェクトのデータを保存するために必要なストリームのサイズを取得します。  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287) Windows SDK にします。  
  
##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew  
 新しく作成されたオブジェクトを初期化します。  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234) Windows SDK にします。  
  
##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty  
 最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092) Windows SDK にします。  
  
##  <a name="load"></a>  IPersistStreamInitImpl::Load  
 オブジェクトのプロパティを指定したストリームから読み込みます。  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を取得します。  
  
 参照してください[IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) Windows SDK にします。  
  
##  <a name="save"></a>  IPersistStreamInitImpl::Save  
 オブジェクトのプロパティを指定したストリームに保存します。  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>コメント  
 ATL は、この情報を格納するのにオブジェクトのプロパティ マップを使用します。  
  
 参照してください[IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [記憶域とストリーム](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [クラスの概要](../../atl/atl-class-overview.md)
