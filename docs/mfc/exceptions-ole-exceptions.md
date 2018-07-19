---
title: '例外処理: OLE 例外 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 991848e9b5b78ad960fb8ed0bdf09dd56db47e2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345542"
---
# <a name="exceptions-ole-exceptions"></a>例外処理 : OLE の例外
テクニックと OLE の例外を処理するための機能は、その他の例外を処理するためのものと同じです。 例外処理の詳細については、記事を参照してください。 [C++ 例外処理](../cpp/cpp-exception-handling.md)です。  
  
 抽象基本クラスから派生したすべての例外オブジェクトは`CException`します。 MFC には、OLE の例外を処理するための 2 つのクラスが用意されています。  
  
-   [COleException](../mfc/reference/coleexception-class.md) OLE の一般例外を処理するためです。  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md)の生成と OLE の処理 (オートメーション) 例外をディスパッチします。  
  
 これら 2 つのクラス間の違いは、それらを提供し、使用されている情報の量です。 `COleException` 例外の OLE ステータス コードを含むパブリック データ メンバーがあります。 `COleDispatchException` 詳細については、次を指定します。  
  
-   アプリケーション固有のエラー コード  
  
-   「ディスクがいっぱいです」など、エラーの説明  
  
-   アプリケーションで使用できるユーザーの追加情報を提供するためのヘルプ コンテキスト  
  
-   アプリケーションのヘルプ ファイルの名前  
  
-   例外を生成したアプリケーションの名前  
  
 `COleDispatchException` Microsoft Visual Basic などの製品と使用できるように、詳細を提供します。 口頭でのエラーの説明は、メッセージ ボックスまたは他の通知で使用できます。ヘルプ情報は、ユーザー例外が発生した条件に応答するために使用できます。  
  
 2 つのグローバル関数が 2 つの OLE 例外クラスに対応して: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception)と[AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception)です。 それぞれ OLE の一般例外と OLE ディスパッチ例外をスローするのにには、それらを使用します。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

