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
ms.openlocfilehash: 7bd0b0cb2c9eb6fe49356ae8fd4602676d54fa66
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622782"
---
# <a name="exceptions-ole-exceptions"></a>例外処理 : OLE の例外

OLE で例外を処理するための手法と機能は、他の例外を処理する場合と同じです。 例外処理の詳細については、「[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)」を参照してください。

すべての例外オブジェクトは、抽象基本クラスから派生 `CException` します。 MFC には、OLE 例外を処理するためのクラスが2つ用意されています。

- [COleException](reference/coleexception-class.md)一般的な OLE 例外を処理します。

- [COleDispatchException](reference/coledispatchexception-class.md)OLE ディスパッチ (オートメーション) の例外を生成および処理するために使用します。

これらの2つのクラスの違いは、提供する情報の量とその使用場所です。 `COleException`には、例外の OLE ステータスコードを含むパブリックデータメンバーがあります。 `COleDispatchException`次のような詳細情報を提供します。

- アプリケーション固有のエラーコード

- "ディスクがいっぱいです" などのエラーの説明

- アプリケーションがユーザーに追加情報を提供するために使用できるヘルプコンテキスト

- アプリケーションのヘルプファイルの名前

- 例外を生成したアプリケーションの名前

`COleDispatchException`Microsoft Visual Basic のような製品で使用できるように、詳細情報を提供します。 メッセージボックスまたはその他の通知では、音声エラーの説明を使用できます。ヘルプ情報は、例外の原因となった条件にユーザーが応答できるようにするために使用できます。

2つのグローバル関数は、 [AfxThrowOleException](reference/exception-processing.md#afxthrowoleexception)と[AfxThrowOleDispatchException](reference/exception-processing.md#afxthrowoledispatchexception)という2つの OLE 例外クラスに対応します。 これらを使用して、一般的な OLE 例外と OLE ディスパッチ例外をそれぞれスローします。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
