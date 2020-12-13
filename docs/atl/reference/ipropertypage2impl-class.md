---
description: '詳細情報: IPropertyPage2Impl クラス'
title: IPropertyPage2Impl クラス
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: 8311746b03c4c680a040c0873ee58f936044dd9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139283"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl クラス

このクラス `IUnknown` はを実装し、 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)の既定の実装を継承します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IPropertyPage2Impl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPropertyPage2Impl:: EditProperty](#editproperty)|プロパティページがアクティブになったときにフォーカスを受け取るプロパティコントロールを指定します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>解説

[IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2)インターフェイスは、メソッドを追加して[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage)を拡張し `EditProperty` ます。 このメソッドを使用すると、クライアントは、プロパティページオブジェクト内の特定のプロパティを選択できます。

クラス `IPropertyPage2Impl` は、の E_NOTIMPL を単に返し `IPropertyPage2::EditProperty` ます。 ただし、 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) の既定の実装を継承し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

プロパティページを作成する場合、通常、クラスはから派生 `IPropertyPageImpl` します。 の追加サポートを提供するには `IPropertyPage2` 、クラス定義を変更し、メソッドをオーバーライドし `EditProperty` ます。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a> IPropertyPage2Impl:: EditProperty

プロパティページがアクティブになったときにフォーカスを受け取るプロパティコントロールを指定します。

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IPropertyPage2:: EditProperty](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) 」を参照してください。

## <a name="see-also"></a>関連項目

[IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
