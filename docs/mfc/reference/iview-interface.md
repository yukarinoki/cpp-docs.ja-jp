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
ms.openlocfilehash: 9233ee5a8330c4b2c79ebc7b79e0616612c00204
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743426"
---
# <a name="iview-interface"></a>IView インターフェイス

[CWinFormsView](../../mfc/reference/cwinformsview-class.md)が、ビュー通知をマネージコントロールに送信するために使用するいくつかのメソッドを実装します。

## <a name="syntax"></a>構文

```
interface class IView
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IView:: Onアクティブビュー](#onactivateview)|ビューがアクティブ化または非アクティブ化されたときに MFC によって呼び出されます。|
|[IView:: OnInitialUpdate](#oninitialupdate)|最初にビューがドキュメントにアタッチされた後、最初にビューが表示される前に、フレームワークによって呼び出されます。|
|[IView:: OnUpdate](#onupdate)|ビューのドキュメントが変更された後に MFC によって呼び出されます。この関数を使用すると、ビューが変更を反映するように表示を更新できます。|

### <a name="remarks"></a>注釈

`IView``CWinFormsView`は、を使用して、共通のビュー通知をホスト型マネージコントロールに転送するいくつかのメソッドを実装します。 これらは、 [OnInitialUpdate](#oninitialupdate)、 [OnUpdate](#onupdate) 、および [onアクティブビュー](#onactivateview)です。

`IView` は [CView](../../mfc/reference/cview-class.md)に似ていますが、はマネージビューおよびコントロールでのみ使用されます。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="requirements"></a>必要条件

ヘッダー: afxwinforms (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a> IView:: Onアクティブビュー

ビューがアクティブ化または非アクティブ化されたときに MFC によって呼び出されます。

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>パラメーター

*アクティブ化*<br/>
ビューがアクティブ化または非アクティブ化されているかどうかを示します。

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a> IView:: OnInitialUpdate

最初にビューがドキュメントにアタッチされた後、最初にビューが表示される前に、フレームワークによって呼び出されます。

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a> IView:: OnUpdate

ビューのドキュメントが変更された後に、MFC によって呼び出されます。

```cpp
void OnUpdate();
```

### <a name="remarks"></a>注釈

この関数を使用すると、ビューが変更を反映するように表示を更新できます。

## <a name="see-also"></a>関連項目

[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)
