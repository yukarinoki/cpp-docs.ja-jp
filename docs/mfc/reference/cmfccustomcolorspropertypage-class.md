---
title: プロパティ ページ クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: 468d947947fc89f9ebc832cda722d854bb8b4be2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752465"
---
# <a name="cmfccustomcolorspropertypage-class"></a>プロパティ ページ クラス

色のダイアログ ボックスでユーザー設定の色を選択できるプロパティ ページを表します。

## <a name="syntax"></a>構文

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|`CMFCCustomColorsPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCCustomColorsPropertyPage::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[プロパティページ::セットアップ](#setup)|プロパティ ページの色コンポーネントを設定します。|

### <a name="remarks"></a>解説

クラス`CMFCColorDialog`は、このクラスを使用して、カスタムカラープロパティページを表示します。 の詳細`CMFCColorDialog`については、「[クラスを表示します](../../mfc/reference/cmfccolordialog-class.md)。

## <a name="example"></a>例

`CMFCCustomColorsPropertyPage`オブジェクトを構築し、プロパティ ページの色のコンポーネントを設定する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[プロパティ ページ](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx カスタムカラーズプロパティページ.h

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>プロパティページ::セットアップ

プロパティ ページの色コンポーネントを設定します。

```cpp
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*R*|[in]RGB 値の赤のコンポーネント。|
|*G*|[in]RGB 値の緑色のコンポーネント。|
|*B*|[in]RGB 値の青いコンポーネント。|

### <a name="remarks"></a>解説

このメソッドは、プロパティ ページの現在の RGB と関連付けられている HLS (色相、明度、および彩度) の色の値を更新します。 [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo)メソッドは、フレームワークが色のダイアログ ボックスを初期化するとき、またはユーザーがマウスの左ボタンを押したときに、このメソッドを呼び出します。 の詳細`CMFCColorDialog`については、「[クラスを表示します](../../mfc/reference/cmfccolordialog-class.md)。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)<br/>
[プロパティ ページ クラス](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
