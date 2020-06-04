---
title: CRecentDockSiteInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::CleanUp
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDefaultPaneDivider
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedPercent
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedRect
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentListOfPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentPaneContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentTabContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::Init
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::IsRecentLeftPane
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SaveListOfRecentPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SetInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::StoreDockInfo
helpviewer_keywords:
- CRecentDockSiteInfo [MFC], CleanUp
- CRecentDockSiteInfo [MFC], GetRecentDefaultPaneDivider
- CRecentDockSiteInfo [MFC], GetRecentDockedPercent
- CRecentDockSiteInfo [MFC], GetRecentDockedRect
- CRecentDockSiteInfo [MFC], GetRecentListOfPanes
- CRecentDockSiteInfo [MFC], GetRecentPaneContainer
- CRecentDockSiteInfo [MFC], GetRecentTabContainer
- CRecentDockSiteInfo [MFC], Init
- CRecentDockSiteInfo [MFC], IsRecentLeftPane
- CRecentDockSiteInfo [MFC], SaveListOfRecentPanes
- CRecentDockSiteInfo [MFC], SetInfo
- CRecentDockSiteInfo [MFC], StoreDockInfo
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
ms.openlocfilehash: 9f23d5aff2bac65363086c077af45e35c3263f65
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750571"
---
# <a name="crecentdocksiteinfo-class"></a>CRecentDockSiteInfo クラス

クラス`CRecentDockSiteInfo`は[、CPane クラス](../../mfc/reference/cpane-class.md)の最新の状態情報を格納するヘルパー クラスです。

## <a name="syntax"></a>構文

```
class CRecentDockSiteInfo : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRecentDockSiteInfo::CleanUp](#cleanup)||
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](#getrecentdefaultpanedivider)||
|[CRecentDockSiteInfo::GetRecentDockedPercent](#getrecentdockedpercent)||
|[CRecentDockSiteInfo::GetRecentDockedRect](#getrecentdockedrect)||
|[CRecentDockSiteInfo::GetRecentListOfPanes](#getrecentlistofpanes)||
|[CRecentDockSiteInfo::GetRecentPaneContainer](#getrecentpanecontainer)||
|[CRecentDockSiteInfo::GetRecentTabContainer](#getrecenttabcontainer)||
|[CRecentDockSiteInfo::Init](#init)||
|[CRecentDockSiteInfo::IsRecentLeftPane](#isrecentleftpane)||
|[コズイントドックサイト情報::演算子 =](#operator_eq)||
|[CRecentDockSiteInfo::SaveListOfRecentPanes](#savelistofrecentpanes)||
|[CRecentDockSiteInfo::SetInfo](#setinfo)||
|[CRecentDockSiteInfo::StoreDockInfo](#storedockinfo)||

## <a name="remarks"></a>解説

`CRecentDockSiteInfo` クラスは、データ管理クラスです。 ドッキング状態とフローティング状態の間で切り替わる `CPane` の最後の状態を追跡します。 ユーザーがフローティング状態のドッキング可能ペインをダブルクリックすると、ペインはドッキング状態になります。 ドッキング状態のペインをダブルクリックすると、ペインは前の位置、サイズ、および状態に戻ります。 同様に、ペインを再びドッキング状態にすると、前のドッキング位置が復元されます。 このデータ クラスは、この機能を実現します。 このクラスのメンバーはドッキング状態のペインの状態情報を格納するため、アプリケーションで直接変更しないでください。

`CRecentDockSiteInfo` オブジェクトは、ペインが作成されるたびに作成されます。 各`CPane`オブジェクトには、この情報を格納するメンバー変数[CPane::m_recentDockInfo](../../mfc/reference/cpane-class.md#m_recentdockinfo)があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrecentDockSiteInfo.h

## <a name="crecentdocksiteinfocleanup"></a><a name="cleanup"></a>コズックドックサイト情報::クリーンアップ

```cpp
void CleanUp();
```

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfocrecentdocksiteinfo"></a><a name="crecentdocksiteinfo"></a>コズ・コズ・ドックサイト情報::コズ・コズ・ドックサイト情報

```
CRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfogetrecentdefaultpanedivider"></a><a name="getrecentdefaultpanedivider"></a>コリストックペイン情報::取得最近のデフォルトペインディバイダー

```
CPaneDivider* GetRecentDefaultPaneDivider();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfogetrecentdockedpercent"></a><a name="getrecentdockedpercent"></a>コズックドックサイトインフォ::最新のドックパーセンテージ

```
int GetRecentDockedPercent(BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfogetrecentdockedrect"></a><a name="getrecentdockedrect"></a>コストドックサイトインフォ::ゲットレコドックドレクト

```
CRect& GetRecentDockedRect(BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfogetrecentlistofpanes"></a><a name="getrecentlistofpanes"></a>ペインの最新リスト

```
CList<HWND, HWND>& GetRecentListOfPanes(BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfogetrecentpanecontainer"></a><a name="getrecentpanecontainer"></a>コネクスドックサイトインフォ::最近のペインコンテナ

```
CPaneContainer* GetRecentPaneContainer(BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfogetrecenttabcontainer"></a><a name="getrecenttabcontainer"></a>コズ・コクズ・ドックサイト情報::最近タブコンテナ

```
CPaneContainer* GetRecentTabContainer(BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfoinit"></a><a name="init"></a>コネクティットドックサイト情報::イニト

```cpp
void Init();
```

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfoisrecentleftpane"></a><a name="isrecentleftpane"></a>コストドックサイトインフォ::イズイストレフトペイン

```
BOOL IsRecentLeftPane(BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfooperator-"></a><a name="operator_eq"></a>コズイントドックサイト情報::演算子 =

```
CRecentDockSiteInfo& operator=(CRecentDockSiteInfo& src);
```

### <a name="parameters"></a>パラメーター

[in]*src*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfosavelistofrecentpanes"></a><a name="savelistofrecentpanes"></a>最近のペイン

```cpp
void SaveListOfRecentPanes(CList<HWND,
    HWND>& lstOrg,
    BOOL bForSlider);
```

### <a name="parameters"></a>パラメーター

[in]*Cリスト<HWND*<br/>
[in]*lstOrg*<br/>
[in]*ビフォースライダー*<br/>

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfosetinfo"></a><a name="setinfo"></a>コズ・コト・ドックサイト情報::セットインフォ

```
virtual void SetInfo(
    BOOL bForSlider,
    CRecentDockSiteInfo& srcInfo);
```

### <a name="parameters"></a>パラメーター

[in]*ビフォースライダー*<br/>
[in]*SRCInfo*<br/>

### <a name="remarks"></a>解説

## <a name="crecentdocksiteinfostoredockinfo"></a><a name="storedockinfo"></a>コストドックサイトインフォ::ストアドックインフォ

```
virtual void StoreDockInfo(
    CPaneContainer* pRecentContainer,
    CDockablePane* pTabbedBar = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*コンテナ*<br/>
[in]*pタブ付きバー*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite クラス](../../mfc/reference/cdocksite-class.md)
