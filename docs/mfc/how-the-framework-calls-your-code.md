---
title: フレームワークと記述したコードとの関係
ms.date: 11/04/2016
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
ms.openlocfilehash: 318ca9558d705ca483d41867a1fe2ad46c36666f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622605"
---
# <a name="how-the-framework-calls-your-code"></a>フレームワークと記述したコードとの関係

ソースコードと MFC フレームワークのコードの関係を理解することが重要です。 アプリケーションの実行時には、ほとんどの制御フローがフレームワークのコードに存在します。 フレームワークは、ユーザーがコマンドを選択してビュー内のデータを編集するときに、Windows からメッセージを取得するメッセージループを管理します。 フレームワーク自体が処理できるイベントは、コードに依存しません。 たとえば、フレームワークは、ウィンドウを閉じる方法と、ユーザーコマンドに応答してアプリケーションを終了する方法を認識しています。 これらのタスクを処理するときに、フレームワークはメッセージハンドラーと C++ 仮想関数を使用して、これらのイベントにも応答できるようにします。 ただし、コードは制御されていません。フレームワークはです。

フレームワークは、アプリケーション固有のイベントのコードを呼び出します。 たとえば、ユーザーがメニューコマンドを選択すると、フレームワークは、現在のビューとフレームウィンドウ、ビューに関連付けられたドキュメント、ドキュメントのドキュメントテンプレート、およびアプリケーションオブジェクトという一連の C++ オブジェクトに沿ってコマンドをルーティングします。 これらのオブジェクトのいずれかがコマンドを処理できる場合は、適切なメッセージハンドラー関数を呼び出します。 特定のコマンドについては、というコードが自分のものである場合もあれば、フレームワークの場合もあります。

このような配置は、Windows またはイベントドリブンプログラミングの従来のプログラミングで経験があるプログラマにとってはよく知られています。

関連トピックでは、フレームワークがアプリケーションを初期化して実行し、アプリケーションの終了に応じてクリーンアップする際の動作について説明します。 また、記述するコードがどこに配置されているかを理解することもできます。

詳細については、「[クラス CWinApp: アプリケーションクラス](cwinapp-the-application-class.md)と[ドキュメントテンプレート」と「ドキュメント/ビューの作成プロセス](document-templates-and-the-document-view-creation-process.md)」を参照してください。

## <a name="see-also"></a>関連項目

[フレームワークでのビルド](building-on-the-framework.md)
