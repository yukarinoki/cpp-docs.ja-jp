---
title: '例外処理 : OLE の例外'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: 2732f571d305fda2b739be02661ab9558f8bc653
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515418"
---
# <a name="exceptions-ole-exceptions"></a>例外処理 : OLE の例外

手法と OLE の例外を処理するための機能は、その他の例外を処理するためのものと同じです。 例外処理の詳細については、記事を参照してください。 [C++ 例外処理](../cpp/cpp-exception-handling.md)します。

すべての例外オブジェクトの抽象基本クラスから派生`CException`します。 MFC には、OLE の例外を処理するための 2 つのクラスが用意されています。

- [COleException](../mfc/reference/coleexception-class.md)全般 OLE の例外を処理するためです。

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md)の生成と OLE の処理 (オートメーション) 例外をディスパッチします。

これら 2 つのクラス間の違いは、それらのもたらすし、が使用されている情報の量です。 `COleException` OLE の例外のステータス コードを含むパブリック データ メンバーがあります。 `COleDispatchException` 詳細については、次を指定します。

- アプリケーション固有のエラー コード

- 「ディスクがいっぱいです」など、エラーの説明

- アプリケーションで使用して、ユーザーの追加情報を提供するためのヘルプ コンテキスト

- アプリケーションのヘルプ ファイルの名前

- 例外を生成したアプリケーションの名前

`COleDispatchException` 詳しくは、Microsoft Visual Basic などの製品と使用できるように説明します。 メッセージ ボックスまたは他の通知では、口頭でのエラーの説明を使用できます。例外の原因となった状況に対応するユーザーを支援するヘルプ情報を使用できます。

2 つのグローバル関数が 2 つの OLE 例外クラスに対応しています: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception)と[AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception)します。 それらを使用して、それぞれ一般的な OLE の例外と OLE ディスパッチの例外をスローします。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

