---
title: IPropertyPage2Impl クラス |Microsoft Docs
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
ms.openlocfilehash: bf5cf9438d2fcecb434802dc99aaa5c692ba108f
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882898"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl クラス
このクラスは実装`IUnknown`の既定の実装の継承と[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IPropertyPage2Impl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。 ATL の実装では、E_NOTIMPL を返します。|  
  
## <a name="remarks"></a>Remarks  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996)インターフェイスは、拡張[IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)を追加して、`EditProperty`メソッド。 このメソッドは、プロパティ ページのオブジェクトで特定のプロパティを選択するクライアントを使用します。  
  
 クラス`IPropertyPage2Impl`の E_NOTIMPL を単純に返します`IPropertyPage2::EditProperty`します。 ただしの既定の実装を継承[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)実装と`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 クラスは一般から派生するプロパティ ページを作成するときに`IPropertyPageImpl`します。 特別なサポートを提供する`IPropertyPage2`、クラス定義を変更し、上書き、`EditProperty`メソッド。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty  
 プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
