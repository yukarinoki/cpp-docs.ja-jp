---
title: CMFCDesktopAlertWndButton クラス |Microsoft Docs
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
ms.openlocfilehash: 9f9993f33386f93ef696213c1721bac5172a2436
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853596"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton クラス
デスクトップ通知ダイアログ ボックスに追加するボタンを使用します。  
  
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
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|警告のダイアログ ボックスのキャプション領域に、ボタンが表示されるかどうかを判断します。|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|ボタンが警告のダイアログ ボックスを閉じるかどうかを判断します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|name|説明|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|警告のダイアログ ボックスのキャプション領域に、ボタンが表示されるかどうかを指定するブール値。|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|ボタンが警告のダイアログ ボックスを閉じるかどうかを指定するブール値。|  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターは既定では、設定、`m_bIsCaptionButton`と`m_bIsCloseButton`データ メンバーを FALSE にします。 親`CMFCDesktopAlertDialog`オブジェクト セット`m_bIsCaptionButton`警告のダイアログ ボックスのキャプション領域で、ボタンが配置されている場合は TRUE にします。 `CMFCDesktopAlertDialog`クラスを作成、`CMFCDesktopAlertWndButton`アラート ダイアログを閉じるボタンとして機能のボックスを設定するオブジェクト`m_bIsCloseButton`を TRUE にします。  
  
 追加`CMFCDesktopAlertWndButton`オブジェクトを`CMFCDesktopAlertDialog`オブジェクトのいずれかのボタンを追加する場合とします。 詳細については`CMFCDesktopAlertDialog`を参照してください[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、使用する方法、`SetImage`メソッドで、`CMFCDesktopAlertWndButton`クラス。 このコード スニペットの一部、[デスクトップ アラート デモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>  CMFCDesktopAlertWndButton::IsCaptionButton  
 警告のダイアログ ボックスのキャプション領域に、ボタンが表示されるかどうかを判断します。  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、警告ダイアログ ボックスのキャプション領域で、ボタンが表示されている場合それ以外の場合、0 を返します。  
  
##  <a name="isclosebutton"></a>  CMFCDesktopAlertWndButton::IsCloseButton  
 ボタンが警告のダイアログ ボックスを閉じるかどうかを判断します。  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンは、警告ダイアログ ボックスを閉じる場合は 0 以外それ以外の場合、0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
