---
title: 'MFC ActiveX コントロール: メソッドからエラー コードのリターン |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43bf6730cf1b914405f99af6572a0a53cd942ac6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354820"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX コントロール : メソッドからのエラー コードのリターン
この記事では、ActiveX コントロールのメソッドからエラー コードを取得する方法を説明します。  
  
 メソッド内でエラーが発生したことを示すために使用する必要があります、 [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror)メンバー関数の場合は、 `SCODE` (状態コード) をパラメーターとして。 事前に定義を使用することができます`SCODE`か、独自のいずれかを定義します。  
  
> [!NOTE]
>  `ThrowError` このプロパティの Get または Set 内のエラーを返すための手段としてのみ使用するものでは関数またはオートメーション メソッドです。 これらは、スタックの適切な例外ハンドラーとなる時間が表示されます。  
  
 ヘルパー関数は、最も一般的な定義済みの存在`SCODE`s など[COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported)、 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)、および[COleControl:。SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted)です。  
  
 一覧については定義済み`SCODE`s とカスタムの定義について`SCODE`s、セクションを参照して[、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)ActiveX コントロール: 高度なトピックです。  
  
 他の領域で、コードの例外を報告の詳細については、次を参照してください。 [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)およびセクション[、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)、ActiveX コントロール: 高度なトピックです。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

