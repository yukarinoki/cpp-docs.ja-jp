---
title: IPropertyPageImpl クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 4f86b93bad181fdbac5763bd215b0ec28ab50296
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365355"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IPropertyPageImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPropertyPageImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ために](#activate)|プロパティ ページ ダイアログ ボックス ウィンドウを作成します。|  
|[IPropertyPageImpl::Apply](#apply)|指定した基になるオブジェクトのプロパティ ページの現在の値を対象`SetObjects`です。 ATL の実装を返します`S_OK`です。|  
|[IPropertyPageImpl::Deactivate](#deactivate)|作成したウィンドウを破棄**Activate**です。|  
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|プロパティ ページの情報を取得します。|  
|[IPropertyPageImpl::Help](#help)|プロパティ ページの Windows のヘルプを起動します。|  
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|アクティブ化されたために、プロパティ ページが変更されたかどうかを示します。|  
|[IPropertyPageImpl::Move](#move)|配置し、プロパティ ページ ダイアログ ボックスのサイズを変更します。|  
|[IPropertyPageImpl::SetDirty](#setdirty)|変更されたか、または変更しないと、プロパティ ページの状態フラグを設定します。|  
|[ために](#setobjects)|配列を提供**IUnknown**プロパティ ページに関連付けられているオブジェクトのポインター。 これらのオブジェクトを呼び出すことによって、プロパティ ページ内の現在の値が表示される**適用**です。|  
|[IPropertyPageImpl::SetPageSite](#setpagesite)|プロパティ ページで、`IPropertyPageSite`プロパティ ページがフレームのプロパティとの通信に使用するポインター。|  
|[IPropertyPageImpl::Show](#show)|プロパティ ページ ダイアログ ボックスは、表示または非表示になります。|  
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|指定されたキーストロークを処理します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|プロパティ ページの状態が変更されたかどうかを指定します。|  
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|プロパティ ページを説明するテキスト文字列に関連付けられたリソース識別子を格納します。|  
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|プロパティ ページに関連付けられているヘルプ トピックのコンテキスト識別子を格納します。|  
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|プロパティ ページを説明するヘルプ ファイルの名前に関連付けられたリソース識別子を格納します。|  
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|プロパティ ページのタブに表示されるテキスト文字列に関連付けられたリソース識別子を格納します。|  
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|プロパティ ページに関連付けられているオブジェクトの数を格納します。|  
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|指す、`IPropertyPageSite`プロパティ ページがフレームのプロパティとの通信に使用するインターフェイスです。|  
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|配列を指す**IUnknown**プロパティ ページに関連付けられているオブジェクトへのポインター。|  
|[IPropertyPageImpl::m_size](#m_size)|プロパティ ページのダイアログ ボックスの幅と高さをピクセル単位で格納します。|  
  
## <a name="remarks"></a>コメント  
 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)インターフェイスは、プロパティ シート内で特定のプロパティ ページを管理するオブジェクトを許可します。 クラス`IPropertyPageImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
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
  
### <a name="remarks"></a>コメント  
 既定では、ダイアログ ボックスがモードレスの値に関係なく、常に、 *bModal*パラメーター。  
  
 参照してください[IPropertyPage::Activate](http://msdn.microsoft.com/library/windows/desktop/ms682250) Windows SDK にします。  
  
##  <a name="apply"></a>  IPropertyPageImpl::Apply  
 指定した基になるオブジェクトのプロパティ ページの現在の値を対象`SetObjects`です。  
  
```
HRESULT Apply();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::Apply](http://msdn.microsoft.com/library/windows/desktop/ms691284) Windows SDK にします。  
  
##  <a name="deactivate"></a>  IPropertyPageImpl::Deactivate  
 ウィンドウを破棄します ダイアログ ボックスで作成された[Activate](#activate)です。  
  
```
HRESULT Deactivate();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms682504) Windows SDK にします。  
  
##  <a name="getpageinfo"></a>  IPropertyPageImpl::GetPageInfo  
 入力、*されている*データ メンバーに含まれる情報を含む構造体。  
  
```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>コメント  
 `GetPageInfo` 関連付けられている文字列リソースを読み込みます[m_dwDocString](#m_dwdocstring)、 [m_dwHelpFile](#m_dwhelpfile)、および[m_dwTitle](#m_dwtitle)です。  
  
 参照してください[文字列](http://msdn.microsoft.com/library/windows/desktop/ms680714)Windows SDK にします。  
  
##  <a name="help"></a>  IPropertyPageImpl::Help  
 プロパティ ページの Windows のヘルプを起動します。  
  
```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::Help](http://msdn.microsoft.com/library/windows/desktop/ms691504) Windows SDK にします。  
  
##  <a name="ipropertypageimpl"></a>  IPropertyPageImpl::IPropertyPageImpl  
 コンストラクターです。  
  
```
IPropertyPageImpl();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを初期化します。  
  
##  <a name="ispagedirty"></a>  IPropertyPageImpl::IsPageDirty  
 アクティブ化されたために、プロパティ ページが変更されたかどうかを示します。  
  
```
HRESULT IsPageDirty(void);
```  
  
### <a name="remarks"></a>コメント  
 `IsPageDirty` 返します`S_OK`がアクティブ化されたため、ページが変更された場合。  
  
##  <a name="m_bdirty"></a>  IPropertyPageImpl::m_bDirty  
 プロパティ ページの状態が変更されたかどうかを指定します。  
  
```
BOOL m_bDirty;
```  
  
##  <a name="m_nobjects"></a>  IPropertyPageImpl::m_nObjects  
 プロパティ ページに関連付けられているオブジェクトの数を格納します。  
  
```
ULONG m_nObjects;
```  
  
##  <a name="m_dwhelpcontext"></a>  IPropertyPageImpl::m_dwHelpContext  
 プロパティ ページに関連付けられているヘルプ トピックのコンテキスト識別子を格納します。  
  
```
DWORD m_dwHelpContext;
```  
  
##  <a name="m_dwdocstring"></a>  IPropertyPageImpl::m_dwDocString  
 プロパティ ページを説明するテキスト文字列に関連付けられたリソース識別子を格納します。  
  
```
UINT m_dwDocString;
```  
  
##  <a name="m_dwhelpfile"></a>  IPropertyPageImpl::m_dwHelpFile  
 プロパティ ページを説明するヘルプ ファイルの名前に関連付けられたリソース識別子を格納します。  
  
```
UINT m_dwHelpFile;
```  
  
##  <a name="m_dwtitle"></a>  IPropertyPageImpl::m_dwTitle  
 プロパティ ページのタブに表示されるテキスト文字列に関連付けられたリソース識別子を格納します。  
  
```
UINT m_dwTitle;
```  
  
##  <a name="m_ppagesite"></a>  IPropertyPageImpl::m_pPageSite  
 指す、 [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583)プロパティ ページがフレームのプロパティとの通信に使用するインターフェイスです。  
  
```
IPropertyPageSite* m_pPageSite;
```  
  
##  <a name="m_ppunk"></a>  IPropertyPageImpl::m_ppUnk  
 配列を指す**IUnknown**プロパティ ページに関連付けられているオブジェクトへのポインター。  
  
```
IUnknown** m_ppUnk;
```  
  
##  <a name="m_size"></a>  IPropertyPageImpl::m_size  
 プロパティ ページのダイアログ ボックスの幅と高さをピクセル単位で格納します。  
  
```
SIZE m_size;
```  
  
##  <a name="move"></a>  IPropertyPageImpl::Move  
 配置し、プロパティ ページ ダイアログ ボックスのサイズを変更します。  
  
```
HRESULT Move(LPCRECT pRect);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::Move](http://msdn.microsoft.com/library/windows/desktop/ms680118) Windows SDK にします。  
  
##  <a name="setdirty"></a>  IPropertyPageImpl::SetDirty  
 フラグのプロパティ ページの状態を変更後または unchanged の値に応じて、として`bDirty`です。  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDirty`  
 [in]場合**TRUE**、プロパティ ページの状態は変更されたものとしてマークします。 それ以外の場合、マークされている、変更します。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、`SetDirty`プロパティ ページが変更されたことをフレームに通知します。  
  
##  <a name="setobjects"></a>  ために  
 配列を提供**IUnknown**プロパティ ページに関連付けられているオブジェクトのポインター。  
  
```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::SetObjects](http://msdn.microsoft.com/library/windows/desktop/ms678529) Windows SDK にします。  
  
##  <a name="setpagesite"></a>  IPropertyPageImpl::SetPageSite  
 プロパティ ページで、 [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583)プロパティ ページがフレームのプロパティとの通信に使用するポインター。  
  
```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::SetPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690413) Windows SDK にします。  
  
##  <a name="show"></a>  IPropertyPageImpl::Show  
 プロパティ ページ ダイアログ ボックスは、表示または非表示になります。  
  
```
HRESULT Show(UINT nCmdShow);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::Show](http://msdn.microsoft.com/library/windows/desktop/ms694467) Windows SDK にします。  
  
##  <a name="translateaccelerator"></a>  IPropertyPageImpl::TranslateAccelerator  
 指定されたキーストロークを処理`pMsg`です。  
  
```
HRESULT TranslateAccelerator(MSG* pMsg);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms686603) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyPage2Impl クラス](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
