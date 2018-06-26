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
ms.openlocfilehash: bdcd18a80b430a0a8576effaaa46215dd5eb9600
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36927920"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX コントロール : メソッドからのエラー コードのリターン
この記事では、ActiveX コントロールのメソッドからエラー コードを取得する方法を説明します。  
  
 メソッド内でエラーが発生したことを示すために使用する必要があります、 [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror)メンバー関数は、パラメーターとして SCODE (状態コード) を取得します。 定義済み SCODE を使用したり、独自のいずれかを定義することができます。  
  
> [!NOTE]
>  `ThrowError` このプロパティの Get または Set 内のエラーを返すための手段としてのみ使用するものでは関数またはオートメーション メソッドです。 これらは、スタックの適切な例外ハンドラーとなる時間が表示されます。  
  
 ヘルパー関数が存在する最も一般的な SCODEs のように定義済みの[COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported)、 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)、および[COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 定義済みの SCODEs とカスタム SCODEs の定義の手順の一覧を参照してください[、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)ActiveX コントロール: 高度なトピックです。  
  
 他の領域で、コードの例外を報告の詳細については、次を参照してください。 [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)およびセクション[、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)、ActiveX コントロール: 高度なトピックです。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

