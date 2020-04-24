---
title: CMFCAcceleratorKey クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: a814618d3bda27d5b4ace12209dd93343ef2eef9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751780"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey クラス

仮想キーのマッピングと書式設定を実装するヘルパー クラス。

## <a name="syntax"></a>構文

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[キー::CMFC アクセラレータキー](#cmfcacceleratorkey)|`CMFCAcceleratorKey` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[キー::フォーマット](#format)|ACCEL 構造体をそのビジュアル表現に変換します。|
|[キー::セットアクセラレータ](#setaccelerator)|オブジェクトのショートカット キーを`CMFCAcceleratorKey`設定します。|

## <a name="remarks"></a>解説

アクセラレータ キーは、ショートカット キーとも呼ばれます。 ユーザーが入力したキーボード ショートカットを表示する場合[、CMFCAcceleratorKeyAssignCtrl クラス](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)は、Alt + Shift + S などのキーボード ショートカットを、"Alt + Shift + S" などのカスタム テキスト形式にマップします。 各`CMFCAcceleratorKey`オブジェクトは、1 つのショートカット キーをテキスト形式にマップします。

ショートカット キーとアクセラレータ テーブルの使用方法の詳細については、「 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)」を参照してください。

## <a name="example"></a>例

オブジェクトの作成方法とメソッドの使用方法を`CMFCAcceleratorKey`次の例に`Format`示します。

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx アクセラレータキー.h

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a>キー::CMFC アクセラレータキー

[オブジェクトを](../../mfc/reference/cmfcacceleratorkey-class.md)構築します。

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>パラメーター

*lpAccel*<br/>
[in]ショートカット キーへのポインター。

### <a name="remarks"></a>解説

ショートカット キーを作成するときにショートカット キーを指定しない`CMFCAccleratorKey`場合は[、CMFCAcceleratorKey::SetAccelerator](#setaccelerator)メソッドを使用して、ショートカット`CMFCAcceleratorKey`キーをオブジェクトに関連付けます。

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a>キー::フォーマット

ACCEL 構造体を関連付けられた文字列値に変換します。

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
[アウト]メソッドが変換された`CString`ショートカット キーを書き込むオブジェクトへの参照。

### <a name="remarks"></a>解説

このメソッドは、関連付けられたショートカット キーの文字列形式を取得します。 コンストラクターまたはメソッド CMFCAcceleratorKey::SetAccelerator を使用して[、CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクトの文字列形式[を](#setaccelerator)設定できます。

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a>キー::セットアクセラレータ

オブジェクトのショートカット[キーを](../../mfc/reference/cmfcacceleratorkey-class.md)設定します。

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>パラメーター

*lpAccel*<br/>
[in]ショートカット キーへのポインター。

### <a name="remarks"></a>解説

このメソッドを使用して、 の作成時に`CMFCAcceleratorKey`ショートカット キーを指定しなかった場合に、 のショートカット`CMFCAcceleratorKey`キーを設定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/ckeyboardmanager-class.md)
