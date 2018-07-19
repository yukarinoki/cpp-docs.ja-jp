---
title: IView インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acf1ba02e9bbf6afd14e41be7dda406d257cb681
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339762"
---
# <a name="iview-interface"></a>IView インターフェイス
いくつかのメソッドを実装する[CWinFormsView](../../mfc/reference/cwinformsview-class.md)を使用してマネージ コントロールを表示通知を送信します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class IView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|ビューがアクティブ化または非アクティブ化されたときに、MFC によって呼び出されます。|  
|[IView::OnInitialUpdate](#oninitialupdate)|ビューが最初に、ドキュメントに接続されているが、ビューが最初に表示される前に、フレームワークによって呼び出されます。|  
|[IView::OnUpdate](#onupdate)|ビューのドキュメントが変更された後に、MFC によって呼び出されますこの関数は、ビューの変更を反映するように表示を更新できます。|  
  
## <a name="remarks"></a>Remarks  
 `IView` いくつかのメソッドを実装する`CWinFormsView`を使用してホストされているマネージ コントロールを一般的な通知の表示を転送します。 これらは[OnInitialUpdate](#oninitialupdate)、 [OnUpdate](#onupdate)と[OnActivateView](#onactivateview)します。  
  
 `IView` ような[CView](../../mfc/reference/cview-class.md)が管理されたビューとコントロールでのみ使用されます。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  

## <a name="requirements"></a>必要条件  
 ヘッダー: afxwinforms.h が (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  

## <a name="onactivateview"></a> IView::OnActivateView  
ビューがアクティブ化または非アクティブ化されたときに、MFC によって呼び出されます。
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>パラメーター
*アクティブ化します。*  
表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  

## <a name="oninitialupdate"></a> IView::OnInitialUpdate
ビューが最初に、ドキュメントに接続されているが、ビューが最初に表示される前に、フレームワークによって呼び出されます。
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate 
ビューのドキュメントが変更された後に、MFC によって呼び出されます。  
```
void OnUpdate();
```
## <a name="remarks"></a>Remarks  
この関数は、ビューの変更を反映するように表示を更新できます。

## <a name="see-also"></a>関連項目  
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)
