---
title: I プロパティページ2Implクラス
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
ms.openlocfilehash: d112a2411a9debbf2eb77e6b851f4500e8d32ab8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329590"
---
# <a name="ipropertypage2impl-class"></a>I プロパティページ2Implクラス

このクラスは、`IUnknown`[実装し、IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)の既定の実装を継承します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPropertyPage2Impl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[I プロパティ ページ2Impl::プロパティの編集](#editproperty)|プロパティ ページがアクティブになったときにフォーカスを受け取るプロパティ コントロールを指定します。 ATL の実装はE_NOTIMPL返します。|

## <a name="remarks"></a>解説

インターフェイスは、メソッド[を](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2)追加することで[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage)を`EditProperty`拡張します。 このメソッドを使用すると、クライアントはプロパティ ページ オブジェクト内の特定のプロパティを選択できます。

クラス`IPropertyPage2Impl`は、単に`IPropertyPage2::EditProperty`E_NOTIMPL を返します。 ただし、デバッグ ビルドでダンプ デバイスに情報を送信`IUnknown`することで[、IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)の既定の実装を継承し、実装します。

プロパティ ページを作成する場合、通常、クラスは`IPropertyPageImpl`から派生します。 の追加サポート`IPropertyPage2`を提供するには、クラス定義を変更し、メソッド`EditProperty`をオーバーライドします。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPropertyPage`

[プロパティ ページ インビジプル](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a>I プロパティ ページ2Impl::プロパティの編集

プロパティ ページがアクティブになったときにフォーカスを受け取るプロパティ コントロールを指定します。

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

「プロパティ[ページ2::編集プロパティ](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを参照しています。](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[クラスを指定します。](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
