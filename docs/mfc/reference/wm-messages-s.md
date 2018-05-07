---
title: 'Wm _ で始まるメッセージのハンドラー: S |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_SIZE [MFC]
- ON_WM_SETFOCUS [MFC]
- ON_WM_SIZING [MFC]
- ON_WM_SYSCHAR [MFC]
- ON_WM_SETTINGCHANGE [MFC]
- ON_WM_SYSDEADCHAR [MFC]
- ON_WM_SHOWWINDOW [MFC]
- ON_WM_STYLECHANGING [MFC]
- ON_WM_SYSCOMMAND [MFC]
- ON_WM_STYLECHANGED [MFC]
- ON_WM_SPOOLERSTATUS [MFC]
- ON_WM_SYSCOLORCHANGE [MFC]
- ON_WM_SETCURSOR [MFC]
- ON_WM_SIZECLIPBOARD [MFC]
- ON_WM_SYSKEYUP [MFC]
- ON_WM_SYSKEYDOWN [MFC]
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b3b7918b74db4e7720f935bcfdf3bf3ffd3d950
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="wm-messages-s"></a>WM_ で始まるメッセージのハンドラー : S
関数プロトタイプに対応するマップ エントリを次に示します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_WM_SETCURSOR に関するページ)|afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *、UINT、UINT) です。|  
|ON_WM_SETFOCUS に関するページ)|afx_msg void [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *) です。|  
|ON_WM_SETTINGCHANGE に関するページ)|afx_msg void [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)(UINT uFlags、LPCTSTR 大文字、小文字以外)|  
|ON_WM_SHOWWINDOW に関するページ)|afx_msg void [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(BOOL、UINT) です。|  
|ON_WM_SIZE に関するページ)|afx_msg void [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT、int, int) です。|  
|ON_WM_SIZECLIPBOARD に関するページ)|afx_msg void [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *、ハンドル)。|  
|ON_WM_SIZING に関するページ)|afx_msg void [OnSizing](../../mfc/reference/cwnd-class.md#onsizing)(UINT、LPRECT) です。|  
|ON_WM_SPOOLERSTATUS に関するページ)|afx_msg void [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)(UINT、UINT) です。|  
|ON_WM_STYLECHANGED に関するページ)|afx_msg void [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(int, LPSTYLESTRUCT) です。|  
|ON_WM_STYLECHANGING に関するページ)|afx_msg void [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)(int, LPSTYLESTRUCT) です。|  
|ON_WM_SYSCHAR に関するページ)|afx_msg void [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)(UINT、UINT、UINT) です。|  
|ON_WM_SYSCOLORCHANGE に関するページ)|afx_msg void [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|  
|ON_WM_SYSCOMMAND に関するページ)|afx_msg void[必ず](../../mfc/reference/cwnd-class.md#onsyscommand); 全体の (UINT、LONG)|  
|ON_WM_SYSDEADCHAR に関するページ)|afx_msg void [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)(UINT、UINT、UINT) です。|  
|ON_WM_SYSKEYDOWN に関するページ)|afx_msg void[持つ](../../mfc/reference/cwnd-class.md#onsyskeydown)(UINT、UINT、UINT) です。|  
|ON_WM_SYSKEYUP に関するページ)|afx_msg void [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)(UINT、UINT、UINT) です。|  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [WM_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)

