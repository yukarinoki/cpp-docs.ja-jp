---
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
ms.openlocfilehash: 5b18a15f8bfd98396acae0558d121b32bc4127c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367626"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton クラス

デスクトップ通知ダイアログボックスにボタンを追加できます。

## <a name="syntax"></a>構文

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|既定のコンストラクターです。|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[ボタン::イスキャプションボタン](#iscaptionbutton)|通知ダイアログ ボックスのキャプション領域にボタンを表示するかどうかを指定します。|
|[ボタン::IsCloseボタン](#isclosebutton)|ボタンが警告ダイアログ ボックスを閉じるかどうかを決定します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|名前|説明|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|通知ダイアログ ボックスのキャプション領域にボタンを表示するかどうかを指定するブール値。|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|ボタンが警告ダイアログ ボックスを閉じるかどうかを指定するブール値。|

### <a name="remarks"></a>解説

既定では、コンストラクターは、`m_bIsCaptionButton`および`m_bIsCloseButton`データ メンバーを FALSE に設定します。 ボタンが`CMFCDesktopAlertDialog`警告ダイアログ`m_bIsCaptionButton`ボックスのキャプション領域に配置されている場合、親オブジェクトは TRUE に設定されます。 この`CMFCDesktopAlertDialog`クラスは、`CMFCDesktopAlertWndButton`警告ダイアログ ボックスを閉じ、TRUE に設定`m_bIsCloseButton`するボタンとして機能するオブジェクトを作成します。

ボタン`CMFCDesktopAlertWndButton`を`CMFCDesktopAlertDialog`追加する場合と同じように、オブジェクトにオブジェクトを追加します。 の詳細`CMFCDesktopAlertDialog`については、「[クラスを表示](../../mfc/reference/cmfcdesktopalertdialog-class.md)します。

## <a name="example"></a>例

クラスでメソッドを使用する方法を`SetImage`次の例に`CMFCDesktopAlertWndButton`示します。 このコード スニペットは[、デスクトップ警告デモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[ボタン](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdesktopalertwnd.h

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a>ボタン::イスキャプションボタン

通知ダイアログ ボックスのキャプション領域にボタンを表示するかどうかを指定します。

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>戻り値

ボタンが警告ダイアログ ボックスのキャプション領域に表示される場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a>ボタン::IsCloseボタン

ボタンが警告ダイアログ ボックスを閉じるかどうかを決定します。

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>戻り値

ボタンが警告ダイアログ ボックスを閉じる場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
