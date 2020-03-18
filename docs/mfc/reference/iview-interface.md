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
ms.openlocfilehash: e8afa7a5f5a7692f88ace4da08209b80f902b603
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445669"
---
# <a name="iview-interface"></a>IView インターフェイス

[CWinFormsView](../../mfc/reference/cwinformsview-class.md)が、ビュー通知をマネージコントロールに送信するために使用するいくつかのメソッドを実装します。

## <a name="syntax"></a>構文

```
interface class IView
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[IView:: Onアクティブビュー](#onactivateview)|ビューがアクティブ化または非アクティブ化されたときに MFC によって呼び出されます。|
|[IView:: OnInitialUpdate](#oninitialupdate)|最初にビューがドキュメントにアタッチされた後、最初にビューが表示される前に、フレームワークによって呼び出されます。|
|[IView:: OnUpdate](#onupdate)|ビューのドキュメントが変更された後に MFC によって呼び出されます。この関数を使用すると、ビューが変更を反映するように表示を更新できます。|

## <a name="remarks"></a>コメント

`IView` は、共通のビュー通知をホストされたマネージコントロールに転送するために `CWinFormsView` 使用するいくつかのメソッドを実装します。 これらは、 [OnInitialUpdate](#oninitialupdate)、 [OnUpdate](#onupdate) 、および[onアクティブビュー](#onactivateview)です。

`IView` は[CView](../../mfc/reference/cview-class.md)に似ていますが、マネージビューおよびコントロールでのみ使用されます。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="requirements"></a>要件

ヘッダー: afxwinforms (アセンブリに定義されています) (アセンブリに定義されています。

## <a name="onactivateview"></a>IView:: Onアクティブビュー

ビューがアクティブ化または非アクティブ化されたときに MFC によって呼び出されます。

```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>パラメーター

*activate*<br/>
ビューがアクティブ化または非アクティブ化されているかどうかを示します。

## <a name="oninitialupdate"></a>IView:: OnInitialUpdate

最初にビューがドキュメントにアタッチされた後、最初にビューが表示される前に、フレームワークによって呼び出されます。

```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView:: OnUpdate

ビューのドキュメントが変更された後に、MFC によって呼び出されます。

```
void OnUpdate();
```

## <a name="remarks"></a>コメント

この関数を使用すると、ビューが変更を反映するように表示を更新できます。

## <a name="see-also"></a>参照

[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)
