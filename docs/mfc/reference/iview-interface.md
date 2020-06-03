---
title: IView インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
ms.openlocfilehash: dfe77699a51ad2670c703d02e13e9062e76debcd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751288"
---
# <a name="iview-interface"></a>IView インターフェイス

マネージ コントロールにビュー通知を送信するために[CWinFormsView](../../mfc/reference/cwinformsview-class.md)が使用するいくつかのメソッドを実装します。

## <a name="syntax"></a>構文

```
interface class IView
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Iビュー::オンアクティブビュー](#onactivateview)|ビューがアクティブまたは非アクティブになったときに MFC によって呼び出されます。|
|[Iビュー::オンイニシャルアップデート](#oninitialupdate)|ビューが最初にドキュメントにアタッチされた後、ビューが最初に表示される前に、フレームワークによって呼び出されます。|
|[IView::オンアップデート](#onupdate)|ビューのドキュメントが変更された後に MFC によって呼び出されます。この関数は、ビューが変更を反映するように表示を更新できるようにします。|

## <a name="remarks"></a>解説

`IView`は、共通のビュー`CWinFormsView`通知をホストされたマネージ コントロールに転送するために使用するいくつかのメソッドを実装します。 これらは、[イニシャルアップデート](#oninitialupdate)、[オンアップデート](#onupdate)、オン[アクティブビューです](#onactivateview)。

`IView`[CView](../../mfc/reference/cview-class.md)に似ていますが、マネージ ビューとコントロールでのみ使用されます。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="requirements"></a>必要条件

ヘッダー: afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a>Iビュー::オンアクティブビュー

ビューがアクティブまたは非アクティブになったときに MFC によって呼び出されます。

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>パラメーター

*アクティブ 化*<br/>
ビューがアクティブ化されているか非アクティブ化されているかを示します。

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a>Iビュー::オンイニシャルアップデート

ビューが最初にドキュメントにアタッチされた後、ビューが最初に表示される前に、フレームワークによって呼び出されます。

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a>IView::オンアップデート

ビューのドキュメントが変更された後に MFC によって呼び出されます。

```cpp
void OnUpdate();
```

## <a name="remarks"></a>解説

この関数を使用すると、ビューの表示を更新して変更を反映できます。

## <a name="see-also"></a>関連項目

[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)
