---
title: CMFCMenuButton クラス
ms.date: 07/15/2019
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
- AFXMENUBUTTON/CMFCMenuButton::m_bDefaultClick
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
- CMFCMenuButton [MFC], m_bDefaultClick
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: 929fc1c8166f249fe3babc724b2c0bcd9cb99676
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369710"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton クラス

ポップアップ メニューを表示してユーザーのメニュー選択を報告するボタンです。

## <a name="syntax"></a>構文

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[メニューボタン::CMFCメニューボタン](#cmfcmenubutton)|`CMFCMenuButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|ウィンドウ メッセージがディスパッチされる前に変換するために、フレームワークによって呼び出されます。 ( `CMFCButton::PreTranslateMessage`をオーバーライドします)。|
|[メニューボタン::サイズコンテンツ](#sizetocontent)|ボタンのテキストとイメージのサイズに応じて、ボタンのサイズを変更します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[メニューボタン::m_bOSMenu](#m_bosmenu)|既定のシステム ポップアップ メニューを表示するか[、CContextMenuManager::トラックポップアップ メニュー](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)を使用するかを指定します。|
|[メニューボタン::m_bRightArrow](#m_brightarrow)|ポップアップ メニューをボタンの下に表示するか、ボタンの右側に表示するかを指定します。|
|[メニューボタン::m_bStayPressed](#m_bstaypressed)|ユーザーがボタンを離した後に、メニュー ボタンの状態を変更するかどうかを指定します。|
|[メニューボタン::m_hMenu](#m_hmenu)|アタッチされた Windows メニューへのハンドル。|
|[メニューボタン::m_nMenuResult](#m_nmenuresult)|ユーザーがポップアップ メニューから選択した項目を示す識別子。|
|[メニューボタン::m_bDefaultClick](#m_bdefaultclick)| 既定の (ボタンのテキスト/イメージ) 処理を許可します。|

## <a name="remarks"></a>解説

クラス`CMFCMenuButton`は[、CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)から派生[します。](../../mfc/reference/cbutton-class.md) したがって、コード内で`CMFCMenuButton`使用するのと同じ方法で使用`CButton`できます。

を作成する場合`CMFCMenuButton`は、関連付けられたポップアップ メニューにハンドルを渡す必要があります。 次に、関数`CMFCMenuButton::SizeToContent`を呼び出します。 `CMFCMenuButton::SizeToContent`ボタンのサイズが、ポップアップ ウィンドウが表示される場所(つまり、ボタンの下または右)を示す矢印を含めるのに十分であることを確認します。

## <a name="example"></a>例

次の例は、ボタンにアタッチされたメニューのハンドルを設定し、ボタンのサイズをテキストとイメージのサイズに応じて変更し、フレームワークによって表示されるポップアップ メニューを設定する方法を示しています。 このコード スニペットは、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmenubutton.h

## <a name="cmfcmenubuttoncmfcmenubutton"></a><a name="cmfcmenubutton"></a>メニューボタン::CMFCメニューボタン

新しい[CMFC メニュー ボタンオブジェクトを](../../mfc/reference/cmfcmenubutton-class.md)構築します。

```
CMFCMenuButton();
```

## <a name="cmfcmenubuttonm_bosmenu"></a><a name="m_bosmenu"></a>メニューボタン::m_bOSMenu

フレームワークに表示されるポップアップ メニューを示すブール型のメンバー変数。

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>解説

TRUE`m_bOSMenu`の場合、フレームワークはこのオブジェクトの`TrackPopupMenu`継承されたメソッドを呼び出します。 それ以外の場合、フレームワーク[は C コンテキスト メニュー マネージャーを](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)呼び出します。

## <a name="cmfcmenubuttonm_brightarrow"></a><a name="m_brightarrow"></a>メニューボタン::m_bRightArrow

ポップアップ メニューの場所を示すブール型のメンバー変数。

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>解説

ユーザーがメニュー ボタンを押すと、アプリケーションにポップアップ メニューが表示されます。 フレームワークは、ボタンの下またはボタンの右側にポップアップ メニューを表示します。 ボタンには、ポップアップ メニューが表示される場所を示す小さな矢印もあります。 TRUE`m_bRightArrow`の場合、フレームワークはボタンの右側にポップアップ メニューを表示します。 それ以外の場合は、ボタンの下にポップアップ メニューが表示されます。

## <a name="cmfcmenubuttonm_bstaypressed"></a><a name="m_bstaypressed"></a>メニューボタン::m_bStayPressed

ユーザーがポップアップ メニューから選択を行っている間に、メニュー ボタンを押して表示するかどうかを示すブール型のメンバー変数。

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>解説

メンバーが`m_bStayPressed`FALSE の場合、使用がボタンをクリックしてもメニュー ボタンが押されることはありません。 この場合、フレームワークはポップアップ メニューのみを表示します。

メンバーが`m_bStayPressed`TRUE の場合、ユーザーがボタンをクリックすると、メニュー ボタンが押されます。 選択またはキャンセルによって、ユーザーがポップアップ メニューを閉じるまで押されたままになります。

## <a name="cmfcmenubuttonm_hmenu"></a><a name="m_hmenu"></a>メニューボタン::m_hMenu

添付されたメニューへのハンドル。

```
HMENU m_hMenu;
```

### <a name="remarks"></a>解説

ユーザーがメニュー ボタンをクリックすると、このメンバー変数で示されるメニューがフレームワークに表示されます。

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>メニューボタン::m_nMenuResult

ユーザーがポップアップ メニューから選択した項目を示す整数。

```
int m_nMenuResult;
```

### <a name="remarks"></a>解説

ユーザーが選択せずにメニューをキャンセルした場合、またはエラーが発生した場合、このメンバー変数の値はゼロになります。

## <a name="cmfcmenubuttonm_bdefaultclick"></a><a name="m_bdefaultclick"></a>メニューボタン::m_bDefaultClick

ボタン上のテキストまたはイメージの既定の処理を許可します。

```
BOOL  m_bDefaultClick;
```

### <a name="remarks"></a>解説

m_bDefaultClickを false に設定すると、ボタンの任意の場所をクリックしたときにボタンがメニューを表示します。

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>メニューボタン::m_nMenuResult

ユーザーがポップアップ メニューから選択した項目を示す整数。

```
int m_nMenuResult;
```

### <a name="remarks"></a>解説

## <a name="cmfcmenubuttonpretranslatemessage"></a><a name="pretranslatemessage"></a>メニューボタン::P再翻訳メッセージ

ウィンドウ メッセージがディスパッチされる前に変換するために、フレームワークによって呼び出されます。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
[in]処理するメッセージを含む[MSG](/windows/win32/api/winuser/ns-winuser-msg)構造体へのポイント。

### <a name="return-value"></a>戻り値

メッセージが変換され、ディスパッチされない場合は 0 以外。メッセージが変換されなかった場合は 0 を返します。

### <a name="remarks"></a>解説

## <a name="cmfcmenubuttonsizetocontent"></a><a name="sizetocontent"></a>メニューボタン::サイズコンテンツ

ボタンのサイズをテキストサイズとイメージサイズに応じて変更します。

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>パラメーター

*唯一の時間*<br/>
[in]このメソッドがボタンのサイズを変更するかどうかを示すブール値パラメーター。

### <a name="return-value"></a>戻り値

ボタンの新しいサイズを指定する[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

### <a name="remarks"></a>解説

この関数を呼び出し *、bCalcOnly* `SizeToContent`が TRUE の場合は、ボタンの新しいサイズのみが計算されます。

ボタンの新しいサイズは、ボタンのテキスト、イメージ、および矢印に合わせて計算されます。 フレームワークは、水平方向のエッジに 10 ピクセル、垂直エッジに 5 ピクセルの定義済みの余白も追加します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcbutton-class.md)
