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
ms.openlocfilehash: c7b60d9e695351e0c1d97b6629ff19664fcd6d05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369941"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl クラス

この`CMFCAcceleratorKeyAssignCtrl`クラスは、Alt、Control、Shift などの追加のシステム ボタンをサポートするように[CEdit クラス](../../mfc/reference/cedit-class.md)を拡張します。

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
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|クラス[CWinApp](../../mfc/reference/cwinapp-class.md)がウィンドウ メッセージを変換するために使用し、[変換メッセージ](/windows/win32/api/winuser/nf-winuser-translatemessage)および[ディスパッチ メッセージ](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows 関数にディスパッチします。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|ショートカット キーをリセットします。|

## <a name="remarks"></a>解説

このクラスは、ショートカット キー (アクセラレータ キーとも呼ばれます) をサポートすることで、`CEdit` クラスの機能を拡張します。 クラス`CMFCAcceleratorKeyAssignCtrl`は[CEdit クラス](../../mfc/reference/cedit-class.md)として機能し、システム ボタンを認識することもできます。

このクラスは、物理的なショートカット キーの組み合わせを文字列値にマップします。 たとえば、キーの組み合わせ Alt + B が文字列 "Alt + B" にマップされている場合、 ユーザーが `CMFCAcceleratorKeyAssignCtrl` オブジェクト内でこのキーの組み合わせを押すと、"Alt + B" が表示されます。 ショートカット キーと文字列形式のマッピングの詳細については、「 [CMFCAcceleratorKey クラス](../../mfc/reference/cmfcacceleratorkey-class.md)」を参照してください。

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

**ヘッダー:** afx アクセラレータキーアカティペンカゲctrl.h

## <a name="cmfcacceleratorkeyassignctrlcmfcacceleratorkeyassignctrl"></a><a name="cmfcacceleratorkeyassignctrl"></a>キー割り当て:::CMFC アクセラレータキーアセプメントCtrl

[オブジェクトを](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)構築します。

```
CMFCAcceleratorKeyAssignCtrl();
```

## <a name="cmfcacceleratorkeyassignctrlgetaccel"></a><a name="getaccel"></a>キー割り当てCtrl::ゲットアッセル

オブジェクトで押`ACCEL`されたショートカット キーの構造[を](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)取得します。

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>戻り値

ショートカット`ACCEL`キーを記述する構造体。

### <a name="remarks"></a>解説

この関数を使用して、`ACCEL`ユーザーがオブジェクトに入力したショートカット キーの構造`CMFCAcceleratorKeyAssignCtrl`を取得します。

## <a name="cmfcacceleratorkeyassignctrlisfocused"></a><a name="isfocused"></a>CMFC アクセラレータキーアビスキーCtrl::フォーカス

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcacceleratorkeyassignctrliskeydefined"></a><a name="iskeydefined"></a>キー割り当て::キー定義

ショートカット キーが[定義](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)されているかどうかを判断します。

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>戻り値

ユーザーが、ショートカット キーを定義する有効なキーの組み合わせを既に押している場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数を使用して、ユーザーがオブジェクトに有効なショートカット キー`CMFCAcceleratorKeyAssignCtrl`を入力したかどうかを確認します。 ショートカット キーが存在する場合は[、CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)メソッドを使用`ACCEL`して、このショートカット キーに関連付けられている構造体を取得できます。

## <a name="cmfcacceleratorkeyassignctrlpretranslatemessage"></a><a name="pretranslatemessage"></a>メッセージを再変換:P

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcacceleratorkeyassignctrlresetkey"></a><a name="resetkey"></a>キー割り当て::リセットキー

ショートカット キーをリセットします。

```
void ResetKey();
```

### <a name="remarks"></a>解説

この関数は、エディット コントロール テキストをクリアします。 これには、ユーザーが押したショートカット キーが含まれます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey クラス](../../mfc/reference/cmfcacceleratorkey-class.md)
