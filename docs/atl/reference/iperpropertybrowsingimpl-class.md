---
title: IPerPropertyBrowsingImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d9fffd6151405eaf53e99f770281139d7664b01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364909"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl クラス
このクラスは実装**IUnknown**クライアント オブジェクトのプロパティ ページの情報にアクセスすることができします。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPerPropertyBrowsingImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|特定のプロパティを説明する文字列を取得します。|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|特定のプロパティで許容される値に対応する文字列の配列を取得します。|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|取得、**バリアント**特定 DISPID によって識別されたプロパティの値を格納します。 DISPID がから取得された文字列名に関連付けられている`GetPredefinedStrings`です。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|特定のプロパティに関連付けられたプロパティ ページの CLSID を取得します。|  
  
## <a name="remarks"></a>コメント  
 [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432)インターフェイスにより、クライアントは、オブジェクトのプロパティ ページの情報にアクセスします。 クラス`IPerPropertyBrowsingImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
> [!NOTE]
>  コンテナー アプリケーションとして Microsoft Access を使用する場合からクラスを派生する必要があります`IPerPropertyBrowsingImpl`です。 それ以外の場合、アクセスは、コントロールを読み込めません。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString  
 特定のプロパティを説明する文字列を取得します。  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) Windows SDK にします。  
  
##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings  
 各配列の 0 個の項目を格納します。  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装の[GetPredefinedValue](#getpredefinedvalue)返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPerPropertyBrowsing::GetPredefinedStrings](http://msdn.microsoft.com/library/windows/desktop/ms679724) Windows SDK にします。  
  
##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue  
 取得、**バリアント**特定 DISPID によって識別されたプロパティの値を格納します。 DISPID がから取得された文字列名に関連付けられている`GetPredefinedStrings`です。  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 ATL の実装の[GetPredefinedStrings](#getpredefinedstrings)対応する文字列が取得されません。  
  
 参照してください[IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) Windows SDK にします。  
  
##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage  
 指定したプロパティに関連付けられたプロパティ ページの CLSID を取得します。  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、この情報を取得します。  
  
 参照してください[IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
