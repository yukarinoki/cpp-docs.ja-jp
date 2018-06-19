---
title: ユーザー定義のハンドラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.handlers
dev_langs:
- C++
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fdc8c70f7ef9bdd04bf40f408c4e014b3e3faa3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373247"
---
# <a name="user-defined-handlers"></a>ユーザー定義のハンドラー
関数プロトタイプに対応するマップ エントリを次に示します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM、LPARAM) です。|  
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM、LPARAM) です。|  
|ON_THREAD_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM、LPARAM) です。|  
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM、LPARAM) です。|  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [WM_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)

