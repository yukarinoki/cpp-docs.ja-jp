---
description: '詳細情報: CMFCAcceleratorKey クラス'
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
ms.openlocfilehash: cb7fc24c4cb4d092c5f109ad892b3778d74a906f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336612"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey クラス

仮想キーのマッピングおよび書式設定を実装するヘルパークラス。

## <a name="syntax"></a>構文

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCAcceleratorKey:: CMFCAcceleratorKey](#cmfcacceleratorkey)|`CMFCAcceleratorKey` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCAcceleratorKey:: Format](#format)|ACCEL 構造体をビジュアル表現に変換します。|
|[CMFCAcceleratorKey:: SetAccelerator](#setaccelerator)|オブジェクトのショートカットキーを設定し `CMFCAcceleratorKey` ます。|

## <a name="remarks"></a>解説

アクセラレータキーは、ショートカットキーとも呼ばれます。 ユーザーが入力したキーボードショートカットを表示する場合、 [CMFCAcceleratorKeyAssignCtrl クラス](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) は、Alt + Shift + s などのキーボードショートカットをカスタムテキスト形式 ("Alt + Shift + s" など) にマップします。 各 `CMFCAcceleratorKey` オブジェクトは、1つのショートカットキーをテキスト形式にマップします。

ショートカットキーとアクセラレータテーブルの使用方法の詳細については、「 [Csee Manager クラス](../../mfc/reference/ckeyboardmanager-class.md)」を参照してください。

## <a name="example"></a>例

次の例は、オブジェクトを構築する方法と、そのメソッドを使用する方法を示して `CMFCAcceleratorKey` `Format` います。

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>要件

**ヘッダー:** afxacceleratorkey

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a> CMFCAcceleratorKey:: CMFCAcceleratorKey

[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクトを構築します。

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>パラメーター

*lpAccel*<br/>
からショートカットキーへのポインター。

### <a name="remarks"></a>解説

を作成するときにショートカットキーを指定しなかった場合は、 `CMFCAccleratorKey` [CMFCAcceleratorKey:: setaccelerator](#setaccelerator) メソッドを使用して、ショートカットキーをオブジェクトに関連付けることができ `CMFCAcceleratorKey` ます。

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a> CMFCAcceleratorKey:: Format

ACCEL 構造体を、関連付けられている文字列値に変換します。

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>パラメーター

*str*<br/>
入出力 `CString` メソッドが変換されたショートカットキーを書き込むオブジェクトへの参照。

### <a name="remarks"></a>解説

このメソッドは、関連付けられているショートカットキーの文字列形式を取得します。 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクトの文字列形式は、コンストラクターまたは[CMFCAcceleratorKey:: setaccelerator](#setaccelerator)メソッドのいずれかを使用して設定できます。

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a> CMFCAcceleratorKey:: SetAccelerator

[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクトのショートカットキーを設定します。

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>パラメーター

*lpAccel*<br/>
からショートカットキーへのポインター。

### <a name="remarks"></a>解説

を作成した `CMFCAcceleratorKey` ときにショートカットキーを指定しなかった場合は、このメソッドを使用してのショートカットキーを設定し `CMFCAcceleratorKey` ます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[Cのマネージャークラス](../../mfc/reference/ckeyboardmanager-class.md)
