---
title: CMFCDesktopAlertWndButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efabaabdcc3f08a58cb7dc0a7845a56e5238548d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370335"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton クラス
デスクトップ通知ダイアログ ボックスに追加するボタンを使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|既定のコンストラクター|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|キャプション領域のアラート ダイアログ ボックスで、ボタンが表示されるかどうかを判断します。|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|ボタンが、[アラート] ダイアログ ボックスを閉じるかどうかを判断します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|キャプション領域のアラート ダイアログ ボックスで、ボタンが表示されるかどうかを指定するブール値。|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|ボタンが、[アラート] ダイアログ ボックスを閉じるかどうかを指定するブール値。|  
  
### <a name="remarks"></a>コメント  
 既定で、コンス トラクターは、設定、`m_bIsCaptionButton`と`m_bIsCloseButton`データ メンバーに`FALSE`です。 親`CMFCDesktopAlertDialog`オブジェクト セット`m_bIsCaptionButton`に`TRUE`アラート ダイアログ ボックスの キャプション 領域で、ボタンが配置されている場合。 `CMFCDesktopAlertDialog`クラスを作成、`CMFCDesktopAlertWndButton`警告のダイアログを閉じるボタンとしてボックスし、設定するオブジェクト。`m_bIsCloseButton`に`TRUE`です。  
  
 追加`CMFCDesktopAlertWndButton`オブジェクトを`CMFCDesktopAlertDialog`オブジェクトのいずれかのボタンを追加する場合とします。 詳細については`CMFCDesktopAlertDialog`を参照してください[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)です。  
  
## <a name="example"></a>例  
 次の例で使用する方法、`SetImage`メソッドで、`CMFCDesktopAlertWndButton`クラスです。 このコード スニペットの一部である、[デスクトップ アラート デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>  CMFCDesktopAlertWndButton::IsCaptionButton  
 キャプション領域のアラート ダイアログ ボックスで、ボタンが表示されるかどうかを判断します。  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 警告のダイアログ ボックスの [キャプション] 領域で、ボタンが表示されている場合は 0 以外。それ以外の場合、0 を返します。  
  
##  <a name="isclosebutton"></a>  CMFCDesktopAlertWndButton::IsCloseButton  
 ボタンが、[アラート] ダイアログ ボックスを閉じるかどうかを判断します。  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ボタン、警告ダイアログ ボックスを閉じます。それ以外の場合、0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
