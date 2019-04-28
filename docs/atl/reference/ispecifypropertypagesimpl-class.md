---
title: ISpecifyPropertyPagesImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 3f5db65d1c318677a630307f44533e51d63ec44d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197420"
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

*T*<br/>
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

## <a name="requirements"></a>必要条件

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

[IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
