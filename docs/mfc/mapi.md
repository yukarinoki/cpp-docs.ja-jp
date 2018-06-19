---
title: MAPI |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19615aabce489049d38539b48300311504fbbbfe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347534"
---
# <a name="mapi"></a>MAPI
この記事では、クライアント メッセージ アプリケーションの開発者向けの Microsoft メッセージング アプリケーション プログラミング インターフェイス (MAPI) について説明します。 MFC クラスで MAPI のサブセットのサポートを提供する**CDocument** API 全体をカプセル化しないが、します。 詳細については、次を参照してください。 [MFC での MAPI サポート](../mfc/mapi-support-in-mfc.md)です。  
  
 MAPI は、一連のメールとメール対応のアプリケーションを作成、操作、転送、およびメール メッセージの保存に使用する関数です。 アプリケーション開発者の目的とメール メッセージの内容を定義するためのツールを使用して、保存したメール メッセージの管理の柔軟性を提供します。 MAPI には、アプリケーション開発者は、メールが有効なを作成に使用できる共通のインターフェイスと、基になるメッセージング システムの独立したメールに対応するアプリケーションも用意されています。  
  
 メッセージング クライアントは、Microsoft Windows メッセージング システム (WMS) との対話のためのヒューマン インターフェイスを提供します。 この連携では、メッセージ ストアとアドレス帳などの MAPI 準拠のプロバイダーからサービスを要求する通常含まれています。  
  
 MAPI の詳細については、Windows SDK のガイドで Win32 MAPI (Messaging) の下にある記事を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [MAPI サポート (MFC で)](../mfc/mapi-support-in-mfc.md)  
  
## <a name="see-also"></a>関連項目  
 [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)   
 [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)   
 [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

