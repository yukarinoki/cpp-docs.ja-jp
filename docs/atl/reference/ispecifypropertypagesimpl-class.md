---
title: ISpecifyPropertyPagesImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74f10684c32cc5b1b4b07ac30406520c9ba41ddd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362233"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`ISpecifyPropertyPagesImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|UUID の配列をカウント値を格納します。 各 UUID は、オブジェクトのプロパティ シートに表示できるプロパティ ページのいずれかの CLSID に対応します。|  
  
## <a name="remarks"></a>コメント  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217)インターフェイスにより、クライアントはオブジェクトでサポートされているプロパティ ページの Clsid の一覧を取得します。 クラス`ISpecifyPropertyPagesImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
> [!NOTE]
>  公開しない、 **ISpecifyPropertyPages**インターフェイスの場合は、オブジェクトがプロパティ ページをサポートしていません。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 配列を入力、 [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048)構造オブジェクトのプロパティ シートに表示できるプロパティ ページの clsid。  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、各 CLSID を取得します。  
  
 参照してください[ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
