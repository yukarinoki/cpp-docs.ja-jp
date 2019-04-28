---
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
ms.openlocfilehash: bf76182242f7b76e3a2c18f85b72674e88afa737
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274777"
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

*T*<br/>
派生したクラス、`IPropertyPage2Impl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。 ATL の実装では、E_NOTIMPL を返します。|

## <a name="remarks"></a>Remarks

[IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2)インターフェイスは、拡張[IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage)を追加して、`EditProperty`メソッド。 このメソッドは、プロパティ ページのオブジェクトで特定のプロパティを選択するクライアントを使用します。

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

参照してください[IPropertyPage2::EditProperty](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage2-editproperty) Windows SDK にします。

## <a name="see-also"></a>関連項目

[IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
