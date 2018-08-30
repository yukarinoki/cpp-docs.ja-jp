---
title: ISpecifyPropertyPagesImpl クラス |Microsoft Docs
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
ms.openlocfilehash: d784d7f3c03b18d2f81d6eec8bc9e4b76c7ee8da
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216770"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl クラス
このクラスは実装`IUnknown`の既定の実装を提供し、 [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages)インターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`ISpecifyPropertyPagesImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|UUID の配列のカウント値を設定します。 各 UUID は、オブジェクトのプロパティ シートに表示できるプロパティ ページのいずれかの CLSID に対応します。|  
  
## <a name="remarks"></a>Remarks  
 [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages)インターフェイスにより、クライアントはオブジェクトでサポートされるプロパティ ページの Clsid の一覧を取得します。 クラス`ISpecifyPropertyPagesImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
> [!NOTE]
>  公開しないで、`ISpecifyPropertyPages`インターフェイスの場合は、オブジェクトがプロパティ ページをサポートしていません。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 配列を格納、 [CAUUID](/windows/desktop/api/ocidl/ns-ocidl-tagcauuid)構造オブジェクトのプロパティ シートに表示できるプロパティ ページの clsid。  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Remarks  
 ATL では、オブジェクトのプロパティのマップを使用して、各 CLSID を取得します。  
  
 参照してください[ISpecifyPropertyPages::GetPages](/windows/desktop/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
