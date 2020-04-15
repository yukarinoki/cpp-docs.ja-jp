---
title: クラスを指定します。
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
ms.openlocfilehash: 06b6b60227a659bd35e042952c7464971fc40bdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326412"
---
# <a name="ispecifypropertypagesimpl-class"></a>クラスを指定します。

このクラスは、`IUnknown`インターフェイスを実装し、既定の実装[を](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages)提供します。

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
から派生したクラス`ISpecifyPropertyPagesImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティ ページの種類::取得ページ](#getpages)|UUID 値のカウントされた配列を埋めます。 各 UUID は、オブジェクトのプロパティ シートに表示できるプロパティ ページの 1 つの CLSID に対応します。|

## <a name="remarks"></a>解説

インターフェイス[を](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages)使用すると、クライアントは、オブジェクトでサポートされているプロパティ ページの CLID の一覧を取得できます。 Class`ISpecifyPropertyPagesImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

> [!NOTE]
> オブジェクトがプロパティ`ISpecifyPropertyPages`ページをサポートしていない場合は、インターフェイスを公開しないでください。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a>プロパティ ページの種類::取得ページ

[CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid)構造体の配列に、オブジェクトのプロパティ シートに表示できるプロパティ ページの CLID を設定します。

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>解説

ATL は、オブジェクトのプロパティ マップを使用して、各 CLSID を取得します。

Windows SDK[の「プロパティページ::GetPages」](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages)を参照してください。

## <a name="see-also"></a>関連項目

[クラスをプロパティページインビ](../../atl/reference/ipropertypageimpl-class.md)<br/>
[クラスを参照しています。](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
