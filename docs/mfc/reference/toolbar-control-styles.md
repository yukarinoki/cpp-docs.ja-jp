---
title: ツール バー コントロールのスタイル
ms.date: 11/04/2016
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
ms.openlocfilehash: eab4dbde68fcebdb0afd0d058b4678c464874c81
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837126"
---
# <a name="toolbar-control-styles"></a>ツール バー コントロールのスタイル

[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md) には、ボタンの外観と動作を決定するスタイルフラグのセットが用意されています。 [CMFCToolBarButton:: system.windows.forms.control.setstyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)を呼び出すことによって、これらのフラグの組み合わせを設定できます。 このトピックでは、スタイルフラグの値とその意味について説明します。

## <a name="property-values"></a>プロパティ値

次の値は、コントロールが表すボタンの種類を決定します。

|名前|説明|
|-|-|
|TBBS_BUTTON|標準のプッシュボタン (既定値)。  |
|TBBS_CHECKBOX|チェックボックスをオンにします。  |
|TBBS_CHECKGROUP|チェックボックスのグループの開始。  |
|TBBS_GROUP|ボタンのグループの先頭。  |
|TBBS_SEPARATOR|セパレーター.  |

次の値は、コントロールの現在の状態を表します。

|名前|説明|
|-|-|
|TBBS_CHECKED|チェックボックスがオンになっています。  |
|TBBS_DISABLED|コントロールが無効になっています。  |
|TBBS_INDETERMINATE|チェックボックスが中間状態です。  |
|TBBS_PRESSED|ボタンが押されています。  |

次の値を指定すると、ツールバーのボタンのレイアウトが変更されます。

|名前|説明|
|-|-|
|TBBS_BREAK|列を分割せずに、新しい行または新しい列に項目を配置します。  |

## <a name="remarks"></a>解説

現在のスタイルは [CMFCToolBarButton:: m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)に格納されます。 を                 `m_nStyle` 呼び出したときに追加の処理を実行する派生クラスもあるので、新しい値を直接設定しないでください `SetStyles` 。

各状態のボタンの外観は、ビジュアルマネージャーによって決定されます。 詳細については、「 [視覚化マネージャー](../../mfc/visualization-manager.md) 」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtoolbarbutton

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[視覚化マネージャー](../../mfc/visualization-manager.md)
