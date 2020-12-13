---
description: '詳細情報: CMFCDesktopAlertWndButton クラス'
title: CMFCDesktopAlertWndButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 0c645f4ec79aaa58364cfa9688d19915ece205bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330076"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton クラス

デスクトップの [警告] ダイアログボックスにボタンを追加できるようにします。

## <a name="syntax"></a>構文

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|既定のコンストラクターです。|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|警告ダイアログボックスのキャプション領域にボタンを表示するかどうかを決定します。|
|[CMFCDesktopAlertWndButton:: IsCloseButton](#isclosebutton)|ボタンが警告ダイアログボックスを閉じるかどうかを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|警告ダイアログボックスのキャプション領域にボタンを表示するかどうかを指定するブール値です。|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|ボタンが警告ダイアログボックスを閉じるかどうかを指定するブール値です。|

### <a name="remarks"></a>解説

既定では、コンストラクターは `m_bIsCaptionButton` および `m_bIsCloseButton` データメンバーを FALSE に設定します。 `CMFCDesktopAlertDialog` `m_bIsCaptionButton` 警告ダイアログボックスのキャプション領域にボタンが配置されている場合、親オブジェクトは TRUE に設定されます。 クラスは、 `CMFCDesktopAlertDialog` `CMFCDesktopAlertWndButton` 警告ダイアログボックスを閉じるボタンとして機能するオブジェクトを作成し、 `m_bIsCloseButton` を TRUE に設定します。

オブジェクト `CMFCDesktopAlertWndButton` をオブジェクトに追加するに `CMFCDesktopAlertDialog` は、任意のボタンを追加します。 の詳細について `CMFCDesktopAlertDialog` は、「 [Cmfcdesktopalertdialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)」を参照してください。

## <a name="example"></a>例

クラスのメソッドを使用する方法を次の例に示し `SetImage` `CMFCDesktopAlertWndButton` ます。 このコードスニペットは、 [デスクトップアラートのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxdesktopalertwnd

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a> CMFCDesktopAlertWndButton::IsCaptionButton

警告ダイアログボックスのキャプション領域にボタンを表示するかどうかを決定します。

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>戻り値

警告ダイアログボックスのキャプション領域にボタンが表示されている場合は0以外。それ以外の場合は0です。

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a> CMFCDesktopAlertWndButton:: IsCloseButton

ボタンが警告ダイアログボックスを閉じるかどうかを決定します。

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>戻り値

ボタンが警告ダイアログボックスを閉じる場合は0以外。それ以外の場合は0です。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
