---
title: CMFCAcceleratorKeyAssignCtrl クラス
ms.date: 10/18/2018
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
ms.openlocfilehash: bd096657de56c0b6daa07004a927b92f1293ddf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454419"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl クラス

`CMFCAcceleratorKeyAssignCtrl`クラスを拡張、 [CEdit クラス](../../mfc/reference/cedit-class.md)alt キーを押し、コントロール、SHIFT などの追加のシステム ボタンをサポートするためにします。

## <a name="syntax"></a>構文

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|`CMFCAcceleratorKeyAssignCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|`CMFCAcceleratorKeyAssignCtrl` オブジェクトで押されるショートカット キーの `ACCEL` 構造体を取得します。|
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|ショートカット キーが定義されているかどうかを判断します。|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|[TranslateMessage](../../mfc/reference/cwinapp-class.md) および [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) で使用されます。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|ショートカット キーをリセットします。|

## <a name="remarks"></a>Remarks

このクラスは、ショートカット キー (アクセラレータ キーとも呼ばれます) をサポートすることで、`CEdit` クラスの機能を拡張します。 `CMFCAcceleratorKeyAssignCtrl`クラスの関数として、 [CEdit クラス](../../mfc/reference/cedit-class.md)とのシステム ボタンを認識できます。

このクラスは、物理的なショートカット キーの組み合わせを文字列値にマップします。 たとえば、キーの組み合わせ Alt + B が文字列 "Alt + B" にマップされている場合、 ユーザーが `CMFCAcceleratorKeyAssignCtrl` オブジェクト内でこのキーの組み合わせを押すと、"Alt + B" が表示されます。 ショートカット キーと文字列の形式の間のマッピングの詳細については、次を参照してください。 [CMFCAcceleratorKey クラス](../../mfc/reference/cmfcacceleratorkey-class.md)します。

## <a name="example"></a>例

次の例は、`CMFCAcceleratorKeyAssignCtrl` オブジェクトを構築し、その `ResetKey` メソッドを使用してショートカット キーをリセットする方法について説明しています。

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxacceleratorkeyassignctrl.h

##  <a name="cmfcacceleratorkeyassignctrl"></a>  CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl

構築、 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)オブジェクト。

```
CMFCAcceleratorKeyAssignCtrl();
```

##  <a name="getaccel"></a>  CMFCAcceleratorKeyAssignCtrl::GetAccel

取得、`ACCEL`でショートカット キーが押されるを構造体、 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)オブジェクト。

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>戻り値

`ACCEL`ショートカット キーを記述する構造体。

### <a name="remarks"></a>Remarks

この関数を使用して、取得、`ACCEL`にユーザーが入力したショートカット キーの構造、`CMFCAcceleratorKeyAssignCtrl`オブジェクト。

##  <a name="isfocused"></a>  CMFCAcceleratorKeyAssignCtrl::IsFocused

詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="iskeydefined"></a>  CMFCAcceleratorKeyAssignCtrl::IsKeyDefined

ショートカット キーが定義されているかどうかを決定する、 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)オブジェクト。

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>戻り値

ユーザーが既に有効なショートカット キーを定義するキーの組み合わせを押した場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を使用して、ユーザーが有効なショートカット キーを入力するかどうかを判断する、`CMFCAcceleratorKeyAssignCtrl`オブジェクト。 ショートカット キーが存在する場合を使用できます[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)メソッドを取得する、`ACCEL`このショートカット キーに関連付けられている構造体。

##  <a name="pretranslatemessage"></a>  CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage

詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

[in]*pMsg*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="resetkey"></a>  CMFCAcceleratorKeyAssignCtrl::ResetKey

ショートカット キーをリセットします。

```
void ResetKey();
```

### <a name="remarks"></a>Remarks

関数は、エディット コントロールのテキストをクリアします。 これには、ユーザーが押されているショートカット キーが含まれます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey クラス](../../mfc/reference/cmfcacceleratorkey-class.md)
