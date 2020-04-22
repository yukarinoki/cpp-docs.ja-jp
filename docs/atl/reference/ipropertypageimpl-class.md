---
title: クラスをプロパティページインビ
ms.date: 11/04/2016
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
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
ms.openlocfilehash: 154bfb5beb258ff26649f44f0bd4c23fb8708977
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745867"
---
# <a name="ipropertypageimpl-class"></a>クラスをプロパティページインビ

このクラスは`IUnknown`[、IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage)インターフェイスの既定の実装を実装し、提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPropertyPageImpl`。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[I プロパティ ページ インビティ::I プロパティ ページ インビ](#ipropertypageimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[I プロパティ ページ インビト::アクティブ化](#activate)|プロパティ ページのダイアログ ボックス ウィンドウを作成します。|
|[I プロパティ ページ インビティ::適用](#apply)|で指定された基になるオブジェクトに現在のプロパティ`SetObjects`ページの値を適用します。 ATL 実装はS_OKを返します。|
|[I プロパティ ページ インビレンビ::Dアクティブ化](#deactivate)|で作成されたウィンドウを`Activate`破棄します。|
|[I プロパティ ページ インビティ::ページ情報](#getpageinfo)|プロパティ ページに関する情報を取得します。|
|[I プロパティ ページ インビレンプラ::ヘルプ](#help)|プロパティ ページの Windows ヘルプを呼び出します。|
|[I プロパティ ページ インビティ::IsPage ダーティ](#ispagedirty)|プロパティ ページがアクティブ化された後に変更されたかどうかを示します。|
|[I プロパティ ページ インビブ::移動](#move)|プロパティ ページのダイアログ ボックスを配置およびサイズ変更します。|
|[I プロパティ ページ インビレンプラ::セットダーティ](#setdirty)|プロパティ ページの状態に変更または変更なしのフラグを設定します。|
|[I プロパティ ページ インプル::セットオブジェクト](#setobjects)|プロパティ ページに`IUnknown`関連付けられているオブジェクトのポインターの配列を提供します。 これらのオブジェクトは、 への呼び出しを通`Apply`じて現在のプロパティ ページの値を受け取ります。|
|[I プロパティ ページ インビッター::ページサイトの設定](#setpagesite)|プロパティ ページがプロパティ`IPropertyPageSite`フレームと通信するポインターをプロパティ ページに提供します。|
|[I プロパティ ページ インビレンプラ::ショー](#show)|プロパティ ページのダイアログ ボックスを表示または非表示にします。|
|[I プロパティ ページ インプル::変換アクセラレータ](#translateaccelerator)|指定したキーストロークを処理します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[I プロパティ ページ インビレンプラ::m_bDirty](#m_bdirty)|プロパティ ページの状態が変更されたかどうかを指定します。|
|[I プロパティ ページ インビレンプラ::m_dwDocString](#m_dwdocstring)|プロパティ ページを記述するテキスト文字列に関連付けられたリソース識別子を格納します。|
|[I プロパティ ページ インビレンプラ::m_dwHelpContext](#m_dwhelpcontext)|プロパティ ページに関連付けられているヘルプ トピックのコンテキスト識別子を格納します。|
|[I プロパティ ページ インビレンプラ::m_dwHelpFile](#m_dwhelpfile)|プロパティ ページを説明するヘルプ ファイルの名前に関連付けられたリソース識別子を格納します。|
|[I プロパティ ページ インビレンプラ::m_dwTitle](#m_dwtitle)|プロパティ ページのタブに表示されるテキスト文字列に関連付けられたリソース識別子を格納します。|
|[I プロパティ ページ インビレンプラ::m_nObjects](#m_nobjects)|プロパティ ページに関連付けられているオブジェクトの数を格納します。|
|[I プロパティ ページ インビレンプラ::m_pPageSite](#m_ppagesite)|プロパティ ページ`IPropertyPageSite`がプロパティ フレームと通信するインターフェイスへのポイント。|
|[I プロパティ ページ インビレンプラ::m_ppUnk](#m_ppunk)|プロパティ ページに関連`IUnknown`付けられているオブジェクトへのポインターの配列へのポインター。|
|[I プロパティ ページ インビレンプラ::m_size](#m_size)|プロパティ ページのダイアログ ボックスの高さと幅をピクセル単位で格納します。|

## <a name="remarks"></a>解説

[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage)インターフェイスを使用すると、オブジェクトはプロパティ シート内の特定のプロパティ ページを管理できます。 Class`IPropertyPageImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ipropertypageimplactivate"></a><a name="activate"></a>I プロパティ ページ インビト::アクティブ化

プロパティ ページのダイアログ ボックス ウィンドウを作成します。

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>解説

既定では、ダイアログ ボックスは *、bModal*パラメータの値に関係なく、常にモードレスです。

[「IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) SDK でアクティブ化する」を参照してください。

## <a name="ipropertypageimplapply"></a><a name="apply"></a>I プロパティ ページ インビティ::適用

で指定された基になるオブジェクトに現在のプロパティ`SetObjects`ページの値を適用します。

```
HRESULT Apply();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

「Windows SDK[で IPropertyPage::適用](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply)する」を参照してください。

## <a name="ipropertypageimpldeactivate"></a><a name="deactivate"></a>I プロパティ ページ インビレンビ::Dアクティブ化

Activate で作成したダイアログ ボックス ウィンドウを[破棄](#activate)します。

```
HRESULT Deactivate();
```

### <a name="remarks"></a>解説

Windows SDK[で「IPropertyPage::Dアクティブ化](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate)する」を参照してください。

## <a name="ipropertypageimplgetpageinfo"></a><a name="getpageinfo"></a>I プロパティ ページ インビティ::ページ情報

データ メンバーに含まれる情報を*pPageInfo*構造体に格納します。

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>解説

`GetPageInfo`[m_dwDocString](#m_dwdocstring)、 [m_dwHelpFile](#m_dwhelpfile)、および[m_dwTitle](#m_dwtitle)に関連付けられた文字列リソースを読み込みます。

「プロパティ[ページ::ゲットページ情報](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo)」を参照してください。

## <a name="ipropertypageimplhelp"></a><a name="help"></a>I プロパティ ページ インビレンプラ::ヘルプ

プロパティ ページの Windows ヘルプを呼び出します。

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>解説

Windows SDK[の「IPropertyPage::ヘルプ](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help)」を参照してください。

## <a name="ipropertypageimplipropertypageimpl"></a><a name="ipropertypageimpl"></a>I プロパティ ページ インビティ::I プロパティ ページ インビ

コンストラクターです。

```
IPropertyPageImpl();
```

### <a name="remarks"></a>解説

すべてのデータ メンバーを初期化します。

## <a name="ipropertypageimplispagedirty"></a><a name="ispagedirty"></a>I プロパティ ページ インビティ::IsPage ダーティ

プロパティ ページがアクティブ化された後に変更されたかどうかを示します。

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>解説

`IsPageDirty`は、ページがアクティブ化されてから変更された場合にS_OKを返します。

## <a name="ipropertypageimplm_bdirty"></a><a name="m_bdirty"></a>I プロパティ ページ インビレンプラ::m_bDirty

プロパティ ページの状態が変更されたかどうかを指定します。

```
BOOL m_bDirty;
```

## <a name="ipropertypageimplm_nobjects"></a><a name="m_nobjects"></a>I プロパティ ページ インビレンプラ::m_nObjects

プロパティ ページに関連付けられているオブジェクトの数を格納します。

```
ULONG m_nObjects;
```

## <a name="ipropertypageimplm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>I プロパティ ページ インビレンプラ::m_dwHelpContext

プロパティ ページに関連付けられているヘルプ トピックのコンテキスト識別子を格納します。

```
DWORD m_dwHelpContext;
```

## <a name="ipropertypageimplm_dwdocstring"></a><a name="m_dwdocstring"></a>I プロパティ ページ インビレンプラ::m_dwDocString

プロパティ ページを記述するテキスト文字列に関連付けられたリソース識別子を格納します。

```
UINT m_dwDocString;
```

## <a name="ipropertypageimplm_dwhelpfile"></a><a name="m_dwhelpfile"></a>I プロパティ ページ インビレンプラ::m_dwHelpFile

プロパティ ページを説明するヘルプ ファイルの名前に関連付けられたリソース識別子を格納します。

```
UINT m_dwHelpFile;
```

## <a name="ipropertypageimplm_dwtitle"></a><a name="m_dwtitle"></a>I プロパティ ページ インビレンプラ::m_dwTitle

プロパティ ページのタブに表示されるテキスト文字列に関連付けられたリソース識別子を格納します。

```
UINT m_dwTitle;
```

## <a name="ipropertypageimplm_ppagesite"></a><a name="m_ppagesite"></a>I プロパティ ページ インビレンプラ::m_pPageSite

プロパティ ページ[がプロパティ](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite)フレームと通信するインターフェイスへのポイント。

```
IPropertyPageSite* m_pPageSite;
```

## <a name="ipropertypageimplm_ppunk"></a><a name="m_ppunk"></a>I プロパティ ページ インビレンプラ::m_ppUnk

プロパティ ページに関連`IUnknown`付けられているオブジェクトへのポインターの配列へのポインター。

```
IUnknown** m_ppUnk;
```

## <a name="ipropertypageimplm_size"></a><a name="m_size"></a>I プロパティ ページ インビレンプラ::m_size

プロパティ ページのダイアログ ボックスの高さと幅をピクセル単位で格納します。

```
SIZE m_size;
```

## <a name="ipropertypageimplmove"></a><a name="move"></a>I プロパティ ページ インビブ::移動

プロパティ ページのダイアログ ボックスを配置およびサイズ変更します。

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>解説

「[プロパティページ::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) SDK での移動」を参照してください。

## <a name="ipropertypageimplsetdirty"></a><a name="setdirty"></a>I プロパティ ページ インビレンプラ::セットダーティ

プロパティ ページの状態に *、bDirty*の値に応じて変更または変更なしのフラグを設定します。

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>パラメーター

*bダーティ*<br/>
[in]TRUE の場合、プロパティ ページの状態は変更済みとしてマークされます。 それ以外の場合は、変更なしとしてマークされます。

### <a name="remarks"></a>解説

必要に応`SetDirty`じて、プロパティ ページが変更されたことをフレームに通知します。

## <a name="ipropertypageimplsetobjects"></a><a name="setobjects"></a>I プロパティ ページ インプル::セットオブジェクト

プロパティ ページに`IUnknown`関連付けられているオブジェクトのポインターの配列を提供します。

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>解説

「[プロパティページ::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) SDK のオブジェクトを設定する」を参照してください。

## <a name="ipropertypageimplsetpagesite"></a><a name="setpagesite"></a>I プロパティ ページ インビッター::ページサイトの設定

プロパティ ページがプロパティ フレームと通信する[IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite)ポインターを持つプロパティ ページを提供します。

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>解説

「Windows SDK[の IPropertyPage::SetPageSite」](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite)を参照してください。

## <a name="ipropertypageimplshow"></a><a name="show"></a>I プロパティ ページ インビレンプラ::ショー

プロパティ ページのダイアログ ボックスを表示または非表示にします。

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>解説

[「プロパティページ::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) SDK で表示する」を参照してください。

## <a name="ipropertypageimpltranslateaccelerator"></a><a name="translateaccelerator"></a>I プロパティ ページ インプル::変換アクセラレータ

で指定されたキーストロークを`pMsg`処理します。

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>解説

Windows SDK[の「IPropertyPage::変換アクセラレータ](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator)」を参照してください。

## <a name="see-also"></a>関連項目

[I プロパティページ2Implクラス](../../atl/reference/ipropertypage2impl-class.md)<br/>
[クラスを参照しています。](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[クラスを指定します。](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
