---
title: IPropertyPageImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b07609b792b7080e2c4c432ed435381007ba286
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075229"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl クラス

このクラスは実装`IUnknown`の既定の実装を提供し、 [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage)インターフェイス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IPropertyPageImpl`します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ために](#activate)|プロパティ ページ ダイアログ ボックス ウィンドウを作成します。|
|[IPropertyPageImpl::Apply](#apply)|指定された基になるオブジェクトにプロパティ ページの現在の値を適用`SetObjects`します。 ATL の実装では、S_OK を返します。|
|[IPropertyPageImpl::Deactivate](#deactivate)|作成されたウィンドウを破棄`Activate`します。|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|プロパティ ページの情報を取得します。|
|[IPropertyPageImpl::Help](#help)|プロパティ ページについては、Windows を起動します。|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|アクティブ化があるために、プロパティ ページが変更されたかどうかを示します。|
|[IPropertyPageImpl::Move](#move)|配置し、プロパティ ページ ダイアログ ボックスのサイズを変更します。|
|[IPropertyPageImpl::SetDirty](#setdirty)|変更されたプロパティ ページの状態フラグを設定します。|
|[ために](#setobjects)|配列を提供します`IUnknown`プロパティ ページに関連付けられたオブジェクトのポインター。 これらのオブジェクトを呼び出すことによって、プロパティ ページ内の現在の値が表示される`Apply`します。|
|[IPropertyPageImpl::SetPageSite](#setpagesite)|プロパティ ページで、`IPropertyPageSite`プロパティ ページがフレームのプロパティとの通信に使用するポインター。|
|[IPropertyPageImpl::Show](#show)|プロパティ ページ ダイアログ ボックスは、表示または非表示になります。|
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|指定されたキーストロークを処理します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|プロパティ ページの状態が変更されたかどうかを指定します。|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|プロパティ ページを説明するテキスト文字列に関連付けられているリソースの識別子を格納します。|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|プロパティ ページに関連付けられたヘルプ トピックのコンテキスト識別子を格納します。|
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|プロパティ ページを説明するヘルプ ファイルの名前に関連付けられたリソース識別子を格納します。|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|プロパティ ページのタブに表示されるテキスト文字列に関連付けられているリソースの識別子を格納します。|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|プロパティ ページに関連付けられたオブジェクトの数を格納します。|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|指す、`IPropertyPageSite`プロパティ ページがフレームのプロパティとの通信に使用するインターフェイス。|
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|配列を指す`IUnknown`プロパティ ページに関連付けられたオブジェクトへのポインター。|
|[IPropertyPageImpl::m_size](#m_size)|ピクセルで高さと幅のプロパティ ページのダイアログ ボックスを格納します。|

## <a name="remarks"></a>Remarks

[IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage)インターフェイスにより、プロパティ シート内の特定のプロパティ ページを管理するオブジェクト。 クラス`IPropertyPageImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl.h

##  <a name="activate"></a>  ために

プロパティ ページ ダイアログ ボックス ウィンドウを作成します。

```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Remarks

既定では、ダイアログ ボックスはモードレスの値に関係なく、常に、 *bModal*パラメーター。

参照してください[IPropertyPage::Activate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-activate) Windows SDK にします。

##  <a name="apply"></a>  IPropertyPageImpl::Apply

指定された基になるオブジェクトにプロパティ ページの現在の値を適用`SetObjects`します。

```
HRESULT Apply();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::Apply](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-apply) Windows SDK にします。

##  <a name="deactivate"></a>  IPropertyPageImpl::Deactivate

作成されたダイアログ ボックス ウィンドウを破棄[Activate](#activate)します。

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::Deactivate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-deactivate) Windows SDK にします。

##  <a name="getpageinfo"></a>  IPropertyPageImpl::GetPageInfo

入力、*されている*データ メンバーに含まれる情報を含む構造体。

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Remarks

`GetPageInfo` 関連付けられている文字列リソースを読み込む[m_dwDocString](#m_dwdocstring)、 [m_dwHelpFile](#m_dwhelpfile)、および[m_dwTitle](#m_dwtitle)します。

参照してください[文字列](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-getpageinfo)Windows SDK にします。

##  <a name="help"></a>  IPropertyPageImpl::Help

プロパティ ページについては、Windows を起動します。

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::Help](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-help) Windows SDK にします。

##  <a name="ipropertypageimpl"></a>  IPropertyPageImpl::IPropertyPageImpl

コンストラクターです。

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Remarks

すべてのデータ メンバーを初期化します。

##  <a name="ispagedirty"></a>  IPropertyPageImpl::IsPageDirty

アクティブ化があるために、プロパティ ページが変更されたかどうかを示します。

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Remarks

`IsPageDirty` アクティブ化があるため、ページが変更された場合は、S_OK を返します。

##  <a name="m_bdirty"></a>  IPropertyPageImpl::m_bDirty

プロパティ ページの状態が変更されたかどうかを指定します。

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>  IPropertyPageImpl::m_nObjects

プロパティ ページに関連付けられたオブジェクトの数を格納します。

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>  IPropertyPageImpl::m_dwHelpContext

プロパティ ページに関連付けられたヘルプ トピックのコンテキスト識別子を格納します。

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>  IPropertyPageImpl::m_dwDocString

プロパティ ページを説明するテキスト文字列に関連付けられているリソースの識別子を格納します。

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>  IPropertyPageImpl::m_dwHelpFile

プロパティ ページを説明するヘルプ ファイルの名前に関連付けられたリソース識別子を格納します。

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>  IPropertyPageImpl::m_dwTitle

プロパティ ページのタブに表示されるテキスト文字列に関連付けられているリソースの識別子を格納します。

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>  IPropertyPageImpl::m_pPageSite

指す、 [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite)プロパティ ページがフレームのプロパティとの通信に使用するインターフェイス。

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>  IPropertyPageImpl::m_ppUnk

配列を指す`IUnknown`プロパティ ページに関連付けられたオブジェクトへのポインター。

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>  IPropertyPageImpl::m_size

ピクセルで高さと幅のプロパティ ページのダイアログ ボックスを格納します。

```
SIZE m_size;
```

##  <a name="move"></a>  IPropertyPageImpl::Move

配置し、プロパティ ページ ダイアログ ボックスのサイズを変更します。

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::Move](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-move) Windows SDK にします。

##  <a name="setdirty"></a>  IPropertyPageImpl::SetDirty

変更されたかの値に応じて、変更しないと、プロパティ ページの状態をフラグ*bDirty*します。

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>パラメーター

*bDirty*<br/>
[in]TRUE の場合、プロパティ ページの状態は変更済みとしてマークされます。 それ以外の場合、マークされているように変更されません。

### <a name="remarks"></a>Remarks

必要に応じて、`SetDirty`プロパティ ページが変更されたことをフレームに通知します。

##  <a name="setobjects"></a>  ために

配列を提供します`IUnknown`プロパティ ページに関連付けられたオブジェクトのポインター。

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::SetObjects](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setobjects) Windows SDK にします。

##  <a name="setpagesite"></a>  IPropertyPageImpl::SetPageSite

プロパティ ページで、 [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite)プロパティ ページがフレームのプロパティとの通信に使用するポインター。

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::SetPageSite](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setpagesite) Windows SDK にします。

##  <a name="show"></a>  IPropertyPageImpl::Show

プロパティ ページ ダイアログ ボックスは、表示または非表示になります。

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::Show](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-show) Windows SDK にします。

##  <a name="translateaccelerator"></a>  IPropertyPageImpl::TranslateAccelerator

指定されたキーストロークを処理`pMsg`します。

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Remarks

参照してください[IPropertyPage::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) Windows SDK にします。

## <a name="see-also"></a>関連項目

[IPropertyPage2Impl クラス](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
