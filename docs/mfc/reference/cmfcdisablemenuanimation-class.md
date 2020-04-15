---
title: CMFCDisableMenuAnimation クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: 990f41d2dfa6491d246797322ee275c9648d52a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367572"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation クラス

ポップアップ メニューのアニメーションを無効にします。

## <a name="syntax"></a>構文

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` オブジェクトを構築します。|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[メニューアニメーション::復元](#restore)|フレームワークがポップアップ メニューの表示に使用した以前のアニメーションを復元します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|名前|説明|
|`CMFCDisableMenuAnimation::m_animType`|前のポップアップ メニューのアニメーションの種類を格納します。|

### <a name="remarks"></a>解説

このヘルパー クラスを使用して、(たとえば、マウスやキーボード コマンドを処理する場合)、ポップアップ メニューのアニメーションを一時的に無効にします。

オブジェクト`CMFCDisableMenuAnimation`は、その有効期間中にポップアップ メニューアニメーションを無効にします。 コンストラクタは、現在のポップアップ メニューのアニメーションタイプをフィールド`m_animType`に格納し、現在のアニメーションタイプ`CMFCPopupMenu::NO_ANIMATION`を に設定します。 デストラクターは、前のアニメーションの種類を復元します。

スタック上にオブジェクト`CMFCDisableMenuAnimation`を作成して、1 つの機能を通じてポップアップ メニューアニメーションを無効にすることができます。 関数間のポップアップメニューアニメーションを無効にする場合は、ヒープ上`CMFCDisableMenuAnimation`にオブジェクトを作成し、ポップアップメニューアニメーションを復元したいときに削除します。

## <a name="example"></a>例

次の例は、スタックを使用してメニュー アニメーションを一時的に無効にする方法を示しています。

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

[アニメーションを無効にする](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpopupmenu.h

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a>メニューアニメーション::復元

フレームワークがポップアップ メニューの表示に使用した以前のアニメーションを復元します。

```
void Restore ();
```

### <a name="remarks"></a>解説

このメソッドは、フレームワークが`CMFCDisableMenuAnimation`ポップアップ メニューを表示するために使用した以前のアニメーションを復元するためにデストラクターによって呼び出されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)
