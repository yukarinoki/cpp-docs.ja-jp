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
ms.openlocfilehash: 97a93e000b3e12d8ec4824100059581216b1b8d9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840766"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation クラス

ポップアップメニューのアニメーションを無効にします。

## <a name="syntax"></a>構文

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` オブジェクトを構築します。|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCDisableMenuAnimation:: Restore](#restore)|フレームワークがポップアップメニューを表示するために使用した前のアニメーションを復元します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|`CMFCDisableMenuAnimation::m_animType`|前のポップアップメニューアニメーションの種類を格納します。|

### <a name="remarks"></a>解説

このヘルパークラスを使用して、ポップアップメニューのアニメーションを一時的に無効にします (マウスやキーボードのコマンドを処理する場合など)。

オブジェクトは、 `CMFCDisableMenuAnimation` 有効期間中のポップアップメニューのアニメーションを無効にします。 コンストラクターは、現在のポップアップメニューのアニメーションの種類をフィールドに格納 `m_animType` し、現在のアニメーションの種類をに設定し `CMFCPopupMenu::NO_ANIMATION` ます。 デストラクターは、前のアニメーションの種類を復元します。

`CMFCDisableMenuAnimation`スタック上にオブジェクトを作成し、1つの関数全体でポップアップメニューのアニメーションを無効にすることができます。 関数間でポップアップメニューのアニメーションを無効にする場合は、 `CMFCDisableMenuAnimation` ヒープ上にオブジェクトを作成し、ポップアップメニューのアニメーションを復元するときにそのオブジェクトを削除します。

## <a name="example"></a>例

次の例は、スタックを使用してメニューアニメーションを一時的に無効にする方法を示しています。

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpopupmenu

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a> CMFCDisableMenuAnimation:: Restore

フレームワークがポップアップメニューを表示するために使用した前のアニメーションを復元します。

```cpp
void Restore ();
```

### <a name="remarks"></a>解説

このメソッドは、フレームワークが `CMFCDisableMenuAnimation` ポップアップメニューを表示するために使用した前のアニメーションを復元するために、デストラクターによって呼び出されます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)
