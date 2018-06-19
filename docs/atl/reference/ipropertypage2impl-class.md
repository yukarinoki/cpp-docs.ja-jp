---
title: IPropertyPage2Impl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 204f62e667bd149dd174f960ba31d8388e01394e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361903"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl クラス
このクラスは実装**IUnknown**の既定の実装の継承と[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPropertyPage2Impl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。 ATL の実装を返します**E_NOTIMPL**です。|  
  
## <a name="remarks"></a>コメント  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996)インターフェイスを拡張[IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)追加することによって、`EditProperty`メソッドです。 このメソッドは、プロパティ ページ オブジェクトで特定のプロパティを選択するクライアントを使用します。  
  
 クラス`IPropertyPage2Impl`を単純に返します**E_NOTIMPL**の**IPropertyPage2::EditProperty**です。 ただし、既定の実装を継承[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)を実装して**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 プロパティ ページを作成するとき、クラスがから派生した通常`IPropertyPageImpl`です。 特別なサポートを提供する**IPropertyPage2**、クラス定義を変更、および上書き、`EditProperty`メソッドです。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty  
 プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
