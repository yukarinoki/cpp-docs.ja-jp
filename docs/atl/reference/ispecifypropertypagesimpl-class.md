---
description: '詳細情報: ISpecifyPropertyPagesImpl クラス'
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
ms.openlocfilehash: 528fafa0473a4aa803e1c1d17a24b2d27584c33a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158050"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl クラス

このクラス `IUnknown` はを実装し、 [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) インターフェイスの既定の実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `ISpecifyPropertyPagesImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl:: GetPages](#getpages)|UUID 値のカウントされた配列を塗りつぶします。 各 UUID は、オブジェクトのプロパティシートに表示できるいずれかのプロパティページの CLSID に対応します。|

## <a name="remarks"></a>解説

[ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages)インターフェイスを使用すると、クライアントは、オブジェクトでサポートされているプロパティページの clsid の一覧を取得できます。 クラス `ISpecifyPropertyPagesImpl` は、このインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

> [!NOTE]
> `ISpecifyPropertyPages`オブジェクトがプロパティページをサポートしていない場合は、インターフェイスを公開しないでください。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a> ISpecifyPropertyPagesImpl:: GetPages

[CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid)構造体の配列に、オブジェクトのプロパティシートに表示できるプロパティページの clsid を設定します。

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>解説

ATL では、オブジェクトのプロパティマップを使用して、各 CLSID を取得します。

Windows SDK の「 [ISpecifyPropertyPages:: GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) 」を参照してください。

## <a name="see-also"></a>関連項目

[IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
